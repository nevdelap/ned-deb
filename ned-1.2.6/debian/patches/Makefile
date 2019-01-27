Description: Makefile for debuild.
 Upstream does not use a Makefile.
 .
 ned (1.2.6-0ubuntu4) cosmic; urgency=low
 .
   * Initial release.
Author: Nev Delap <nevdelap@gmail.com>
Last-Update: 2019-01-27

--- /dev/null
+++ ned-1.2.6/Makefile
@@ -0,0 +1,22 @@
+# Makefile for deb package build.
+
+prefix = /usr
+
+build: target/release/ned
+
+target/release/ned: Cargo.* src/*.rs
+	CARGO_HOME=`mktemp -d` cargo build --release --locked
+
+.PHONY: test
+
+test:
+	CARGO_HOME=`mktemp -d` cargo test --release --locked
+
+install: target/release/ned
+	$(INSTALL) -s -Dm755 target/release/ned $(DESTDIR)$(prefix)/bin/ned
+
+uninstall:
+	-rm $(DESTDIR)$(prefix)/bin/ned
+
+clean:
+	cargo clean --release
