all: pam-0.0.1.zip zsh-0.0.1.zip

pam-0.0.1.zip:
	rm -f $@
	cd pamd && zip -r ../$@ .

zsh-0.0.1.zip:
	rm -f $@
	cd zsh && zip -r ../$@ .

clean:
	rm -f *.zip

.PHONY: all zip-0.0.1.zip pam-0.0.1.zip clean
