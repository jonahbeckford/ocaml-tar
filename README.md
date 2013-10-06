Simple library to read and write tar files with an emphasis on streaming.

This is pure OCaml code, no C bindings.

Example toplevel session
========================

In utop:
```
utop # #require "tar";;
utop # #require "tar.lwt";;

utop # lwt f = Lwt_unix.openfile "/tmp/foo.tar" [ Unix.O_RDONLY ] 0 ;;
val f : Lwt_unix.file_descr = <abstr> 

utop # Tar_lwt_unix.Archive.list f;;
[{Tar_lwt_unix.Header.file_name = "_build/lib/tar.mli.depends";
  Tar_lwt_unix.Header.file_mode = 420; Tar_lwt_unix.Header.user_id = 1000;
  Tar_lwt_unix.Header.group_id = 1000; Tar_lwt_unix.Header.file_size = 21L;
  Tar_lwt_unix.Header.mod_time = 1381080315L;
  Tar_lwt_unix.Header.link_indicator = Tar_lwt_unix.Header.Link.Normal;
  Tar_lwt_unix.Header.link_name = ""};
 {Tar_lwt_unix.Header.file_name = "_build/lib/tar_unix.mli.depends";
  Tar_lwt_unix.Header.file_mode = 420; Tar_lwt_unix.Header.user_id = 1000;
  Tar_lwt_unix.Header.group_id = 1000; Tar_lwt_unix.Header.file_size = 27L;
  Tar_lwt_unix.Header.mod_time = 1381080318L;
  Tar_lwt_unix.Header.link_indicator = Tar_lwt_unix.Header.Link.Normal;
  Tar_lwt_unix.Header.link_name = ""};
 {Tar_lwt_unix.Header.file_name = "_build/lib/tar.mllib";
  Tar_lwt_unix.Header.file_mode = ...; Tar_lwt_unix.Header.user_id = ...;
  Tar_lwt_unix.Header.group_id = ...; Tar_lwt_unix.Header.file_size = ...;
  Tar_lwt_unix.Header.mod_time = ...; Tar_lwt_unix.Header.link_indicator = ...;
  Tar_lwt_unix.Header.link_name = ...};
 ...]
```
