To bundle a zip into an asset file for distribution, run `make`. This will

* bundle the sub-directories into a `.zip` archive called e.g. `pam-0.0.1.zip`
* SHA-256 this and update the asset declaration in `../assets`

If you already have `.zip` files built you may need to `make clean` to regenerate them.