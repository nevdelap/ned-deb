Description: Makefile for debuild.
 Upstream does not use a Makefile.
 .
 ned (1.2.6-0) cosmic; urgency=low
 .
   * Initial release.
Author: Nev Delap <nevdelap@gmail.com>
Last-Update: 2019-01-31

--- /dev/null
+++ ./Makefile
@@ -0,0 +1,22 @@
+# Makefile for deb package build.
+
+prefix = /usr
+
+build: target/release/ned
+
+target/release/ned: Cargo.* src/*.rs
+	PATH="/home/nev/.cargo/bin:$$PATH" cargo build --release --target `uname -p`-unknown-linux-musl --locked
+
+.PHONY: test
+
+test:
+	PATH="/home/nev/.cargo/bin:$$PATH" cargo test --release --target `uname -p`-unknown-linux-musl --locked
+
+install: target/release/ned
+	$(INSTALL) -s -Dm755 target/`uname -p`-unknown-linux-musl/release/ned $(DESTDIR)$(prefix)/bin/ned
+
+uninstall:
+	-rm $(DESTDIR)$(prefix)/bin/ned
+
+clean:
+	PATH="/home/nev/.cargo/bin:$$PATH" cargo clean --release --target `uname -p`-unknown-linux-musl
