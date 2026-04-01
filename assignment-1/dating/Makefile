dating-server:
	$(TROUPE)/bin/troupec dating-server.trp -o ./out/dating-server.js
	node $(TROUPE)/rt/built/troupe.js -f=./out/dating-server.js --id=../ids/id-server.json --trustmap=../trustmaps/GoT.json --aliases=aliases.json

dating-client:
	$(TROUPE)/bin/troupec dating-client.trp -o ./out/dating-client.js
	node $(TROUPE)/rt/built/troupe.js -f=./out/dating-client.js --trustmap=../trustmaps/client.json --aliases=aliases.json

clients:
	@echo "Starting Alice and Bob..."
	# Build Alice and run in background
	$(TROUPE)/bin/troupec alice.trp -o ./out/alice.js
	node $(TROUPE)/rt/built/troupe.js -f=./out/alice.js --trustmap=../trustmaps/client.json --aliases=aliases.json & \
	
	# Build Bob and run in background
	$(TROUPE)/bin/troupec bob.trp -o ./out/bob.js
	node $(TROUPE)/rt/built/troupe.js -f=./out/bob.js --trustmap=../trustmaps/client.json --aliases=aliases.json & \
	
	# Wait for both background processes to finish
	wait