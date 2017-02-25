# RustSec Advisory Database

The RustSec Advisory Database is a repository of security advisories filed
against Rust crates published via https://crates.io

Advisory metadata is stored in [TOML] format for [cargo-audit] and other
automated tools to consume.

## Format

Each advisory contains information in [TOML] format:

```toml
[vulnerability]
package = "mypackage"
versions = ["1.2.0", "1.2.3", "1.2.4", "1.2.5"]

# It is strongly recommended to request a CVE, or alternatively a DWF, and
# reference the assigned number here.
# - CVE: https://iwantacve.org/
# - DWF: https://distributedweaknessfiling.org/
dwf = []
# dwf = ["CVE-YYYY-XXXX"]
# dwf = ["CVE-YYYY-XXXX", "CVE-ZZZZ-WWWW"]

# URL to a long-form description of this issue, e.g. a blogpost announcing
# the release or a changelog entry (optional)
url = false

# Enter a short-form description of the vulnerability here (required)
description = """
Affected versions of this crate did not properly X.

This allows an attacker to Y.
 
The flaw was corrected by Z.
"""
```

[TOML]: https://github.com/toml-lang/toml
[cargo-audit]: https://github.com/rustsec/cargo-audit