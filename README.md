
# Git LFS server

Simple HTTP(S) server for [Git Large File Storage](https://git-lfs.github.com).

```
$ ./lfs_server -help
Start Git LFS server

  lfs_server [ROOT]

=== flags ===

  [-cert file]   File of certificate for https
  [-key file]    File of private key for https
  [-p port]      TCP port to listen on
  [-s address]   IP address to listen on
  [-build-info]  print info about this build and exit
  [-version]     print the version of this build and exit
  [-help]        print this help text and exit
                 (alias: -?)
```
By default, it starts on `http://localhost:8080` and treats current directory as `ROOT`. All object files are stored locally in `ROOT/.lfs/objects` directory.

## TODO
* Rearrange files in release package and remove redundant libs
* Check SIGQUIT and SIGINT are handled correctly
* Add logging
* Remove incomplete/broken temporary files
* Upload validation (calculate SHA-256 digest)
* Backup objects
* Fix HTTPS urls
* Multi server support
* Automated tests
* Authentication
* ~~HTTPS support (trivial to add)~~
* ~~Speed-up uploading~~ (fixed in `cohttp`, see [#330](https://github.com/mirage/ocaml-cohttp/pull/330))
