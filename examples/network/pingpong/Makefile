MKID=node $(TROUPE)/rt/built/p2p/mkid.js
MKALIASES=node $(TROUPE)/rt/built/p2p/mkaliases.js
START=$(TROUPE)/network.sh

zero.listener1:
	$(START) zero.trp --id=ids/pingpong-listener1.json --rspawn=true --aliases=aliases.json --stdiolev={} # --debug --debugp2p

zero.listener2:
	$(START) zero.trp --id=ids/pingpong-listener2.json --rspawn=true --aliases=aliases.json --stdiolev={} # --debug --debugp2p

pingpong.dialer:
	$(START) p2ppingpong.trp --id=ids/pingpong-dialer.json --aliases=aliases.json # --debug --debugp2p

create-network-identifiers:
	mkdir -p ids 
	$(MKID) --outfile=ids/pingpong-listener1.json
	$(MKID) --outfile=ids/pingpong-listener2.json
	$(MKID) --outfile=ids/pingpong-dialer.json
	$(MKALIASES) --include ids/pingpong-listener1.json --include ids/pingpong-listener2.json --include ids/pingpong-dialer.json --outfile aliases.json
