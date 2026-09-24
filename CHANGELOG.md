
## [unreleased]

### 🚀 Features

- Add ara-sec Rust security engine (Phase 1)
- *(ara-sec)* Implement static analysis engine (Phase 2)
- *(cli)* Add analyze/audit commands with ara-sec integration
- Bundle script and side-by-side binary delivery
- Add src-rs Rust foundation (types + hash) alongside Zig
- Move ara-sec analysis engine into src-rs
- Port manifest and lockfile (types + parser + generator)
- Port store (CAS) and resolver (graph + MVS)
- Port sources (local, workspace, git, github, registry) + HTTP client
- Port sandbox (profiles + executor with Linux seccomp)
- Port CLI (analyze, audit, install, run) with clap, replace IPC with direct analysis calls
- Wire sandbox into run, add store cache + graph_hash + security meta to install, parser validation, clean dead code
- Connect source::resolve, has_cycles, compute_hash, gc command, find_node, and parser validation
- Add cliff
- *(manifest)* Add kind field to DependencyEntry
- *(manifest)* Add package.json parser module
- *(cli)* Auto-detect package.json in install command
- *(manifest)* Add package.json generator and remove dead code warnings
- *(tests)* Add fixture-based test harness with 39 scenarios (#8)
- Implement ara install <spec> for direct package install (RFC-002) (#10)
- *(store-efficiency)* Atomic operations, integrity checks, sharding, SQLite index, and full GC (#15)
- *(workspace-protocol)* Parse workspace: prefix, live symlinks, and e2e tests (#16)
- Add CodSpeed continuous benchmarking CI and add +3 fixtures e2e tests (#24)
- Reduce security scanner noise by skipping .d.ts files and auto-approving low-risk packages (#25)
- *(install)* Add --package-lock flag to generate package-lock.json (#27)
- Add changelog bot workflow (#35)
- Improved parser error messages and security performance (#42)
- Add real-time progress bars during install (#43)
- Add workspace catalog support and related CLI commands (#59)
- *(cli)* Add --profile flag to ara x with OS-aware default (#66)

### 🐛 Bug Fixes

- Adapt to Zig 0.13 API changes (writeFile, epoch, getenv, Child.init)
- E2e and unit tests passing
- Pre-commit hook path (remove bogus /ara suffix)
- Use 'zig test src/main.zig' instead of 'zig build test' for speed
- *(resolver)* Correct MVS algorithm, propagate hash errors, add supply-chain CI
- *(security)* Block path traversal in CAS store, add HTTP retry, unify analyze/audit and add build inject version
- Pre-commit
- *(ci)* Remove working directory
- Change native-tls to rustls-tls, to eliminate deps of open ssl
- Sec
- Deny
- *(manifest)* Escape TOML output and support workspace object form
- *(registry)* Respect dist-tags.latest and fix tarball URLs with prerelease (#11)
- *(registry)* Correct tarball URL for scoped npm packages (@scope/name) (#12)
- Build windows
- *(readme)* Translate Portuguese examples to English
- *(robustness)* Prevent silent data loss in legacy index migration and lockfile reads (#17)
- *(robustness)* Propagate write_lockfile errors and gate graph cleanup behind --aggressive (#18)
- *(robustness)* Add warnings to silent error paths in install and resolver (#19)
- Distinguish 404, parse errors, and network errors in registry source (#20)
- Add input validation for manifest and lockfile (#21)
- *(deps)* Update rust crate toml to v1 (#32)
- Respect version constraints and handle prerelease/compound ranges (#34)
- Handle shorthand versions and operator whitespace in constraint parsing (#38)
- *(security)* Sandbox hardening, HTTP enforcement, tarball/file/workspace validation, SRI propagation (#44)
- *(cli)* Isolate store per test run and scope cache key with registry URL (#47)
- *(cli)* Resolve symlink-based TOCTOU in tarball extraction (#64)
- *(cli)* Prevent tar unpack from following symlinks (#65)

### 💼 Other

- Initial project structure with build.zig and skeleton
- Add fundamental types, version, constraint, source types, and hash utility
- Add minimal TOML parser with table and array-of-tables support
- Add inline table parsing with memory management
- Add array value support in parser
- Add manifest parser with project, deps, workspace, scripts, security, build
- Add parser and generator for ara.lock
- Implement content-addressed storage with put/get/dedup
- Add source abstraction with workspace, local, git, github, registry stubs
- Implement MVS resolver with constraint collection and graph building
- Add CLI entrypoint with install, run commands and argument parsing
- Add sandbox profiles (open/restricted/hermetic/custom) and executor
- Implement HTTP client with std.http.Client
- Implement real fetch for all sources (HTTP, git CLI, local)
- Complete pipeline with fetch, CAS store, materialize, and lockfile
- Add JSON-RPC layer for Zig ↔ Rust subprocess communication
- Add workspace to lsp resolver
- Testes, clippy, lint, doc comments e Makefile para src-rs
- Bump to v0.2.0
- Bump to v0.3.0
- Bump to v0.4.0
- Bump to v0.4.1"
- Bump to v0.6.0
- Bump to v0.7.0
- Bump to v0.8.0
- Bump to v0.9.1
- Bump to v0.10.0
- Bump to v0.11.0
- Add instructions for AI agents (#46)
- Bump to v0.13.0
- *(sandbox)* [Fix security issues in sandbox] seccomp-BPF, path traversal, and more (#61)
- Bump to v0.13.1

### 🚜 Refactor

- Replace hand-rolled date math, semver parser, and unify source types
- Migrate to Cargo Workspaces with multi-crate structure (#40)
- Split install.rs (#60)

### 📚 Documentation

- Add readme
- Uodate readme
- *(readme)* Document direct package install (ara install <spec>)
- *(readme)* Document workspace protocol, live symlinks, and hybrid manifests
- Document --package-lock flag in README
- Populate CHANGELOG with all releases from v0.1.0 to v0.9.1
- Update CHANGELOG.md (#36)
- Update CHANGELOG.md (#41)
- Update CHANGELOG.md (#45)
- Update CHANGELOG.md (#62)

### ⚡ Performance

- Optimize Phase 3b installation with concurrency and streaming extraction (#23)
- Speed up install phase 3b by 7x with HTTP/2 warmup, larger window, and batch SQLite inserts (#26)

### 🧪 Testing

- Add error, allocator, generative, and comptime tests
- Add more tests (#22)

### ⚙️ Miscellaneous Tasks

- Add make file, tests and fixtures
- Update test
- Remove ara-sec from pre commit hook
- Format code
- Format code
- Remove legacy code and prepare codebase
- Resolve dead code
- Format code
- Organize src
- Add fmt check in pre commit hook
- Add step check fmt in hook
- Add license
- Add cargo-dist
- Add ci pipeline"
- Change repo owner
- Run release automatically
- Fix multilines
- *(makefile)* Add install target for local binary
- Add Renovate dependency update config
- Update changelog
