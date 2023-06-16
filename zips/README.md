To bundle a zip into an asset file for distribution, follow these steps:

* cd into the directory named for the service is is managing (`zsh` in this example)

`cd zsh`
* Modify the files as needed
* Zip it up and write it out to the parent directory

`zip -r ../zsh-0.0.1.zip .`

* Upload the zip to a cloud storage bucket of your choice which is publicly accessible
* If you would like to use example files, the ddm examples in this repo already contain valid zip files and hashes

