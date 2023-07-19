URL="https://files.macadmins.io"
AUTH_TYPE="None"

all: \
	bash-0.0.1.zip \
	myservice-0.0.1.zip \
	pam-0.0.1.zip \
	sshd-0.0.1.zip \
	sudo-0.0.1.zip \
	zsh-0.0.1.zip

# the individual targets for file-up-to-date checking
bash-0.0.1.zip: $(shell find bash -type f)
myservice-0.0.1.zip: $(shell find myservice -type f)
pam-0.0.1.zip: $(shell find pam -type f)
sshd-0.0.1.zip: $(shell find sshd -type f)
sudo-0.0.1.zip: $(shell find sudo -type f)
zsh-0.0.1.zip: $(shell find zsh -type f)

%-0.0.1.zip: %
	rm -f $@
	cd $< && zip -r ../$@ .
	cat ../assets/io.macadmins.asset.$<.json > /tmp/decl.tmp.json
	jq --tab '.Payload.Reference."Hash-SHA-256" = "'$$(shasum -a 256 $@ | awk '{print $$1}')'" | .Payload.Reference.DataURL = "'$(URL)/$@'" | .Authentication.Type = "'$(AUTH_TYPE)\" /tmp/decl.tmp.json > /tmp/decl.tmp.upd.json
	cp /tmp/decl.tmp.upd.json ../assets/io.macadmins.asset.$<.json
	rm /tmp/decl.tmp.json /tmp/decl.tmp.upd.json

clean:
	rm -f *.zip

.PHONY: all clean
