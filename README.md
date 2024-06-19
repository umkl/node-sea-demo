# Creating a SEA with nodejs

As it ain't usual for scripting languages like Javascript to compile code into a single executable, creating CLIs can be quite tidious.

With Node 20 the feature to create SEAs - Single Executable Applications - was released and now it is possible to create executables by injecting the node executable into a blob with your compiled code.

Step 1: define sea-config file
Step 2: get a copy of the node executable to run your js code: ` cp $(command -v node) node_stuff`
Step 3: run this to inject the blob into the executable: `
npx postject node_stuff NODE_SEA_BLOB sea-prep.blob \
 --sentinel-fuse NODE_SEA_FUSE_fce680ab2cc467b6e072b8b5df1996b2 \
 --macho-segment-name NODE_SEA`
Step 4: execute node_stuff
