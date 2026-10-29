# OpenSSL - llm port

Original project: [OpenSSL](https://github.com/openssl/openssl), version 3.5.9.
Original authors: the [OpenSSL Project Authors and contributors](https://github.com/openssl/openssl/blob/openssl-3.5.9/AUTHORS.md).
[Original repository](https://github.com/openssl/openssl).

The library is the work of its original authors, not a product of llm-build-system.
This repository only maintains its llm build integration and source subset.
It is not an official upstream release. Upstream source and header files are
unchanged. Build configuration files added by this port are kept separately.
Upstream build systems, command-line tools, tests and manuals are omitted.

The original license is preserved verbatim in [LICENSE](LICENSE).
[Upstream license](https://github.com/openssl/openssl/blob/openssl-3.5.9/LICENSE.txt). Copyright and per-file license notices
remain in the original files.

Build the static library with `llm build --release`. Consumers include the
usual `<openssl/...>` headers. The single archive contains both libssl
and libcrypto APIs, so llm consumers need only one dependency.
Upstream-generated public headers, provider tables and the five native
target configurations are supplied with the port.
The pinned profile uses upstream portable C implementations, builtin
default/legacy providers, OS entropy, no dynamic provider modules and no
automatic configuration loading, matching llm's existing dependency build.
Configuration and reproducible build-identification headers added by the
port are separate from the unchanged upstream implementations.
