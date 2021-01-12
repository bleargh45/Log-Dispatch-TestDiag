# NAME

Log::Dispatch::TestDiag - Log to Test::More's diagnostic output

# SYNOPSIS

```perl
use Log::Dispatch;

my $logger = Log::Dispatch->new(
    outputs => [
        ['TestDiag', min_level=>'debug', as_note=>0],
    ],
);
```

# DESCRIPTION

This module provides a `Log::Dispatch` output that spits the logged records out
using `Test::More`'s diagnostic output.

# METHODS

- new()

    Constructs a new `Log::Dispatch::TestDiag` object and returns it to the caller.
    Accepts standard `Log::Dispatch::Output` parameters (e.g. `min_level`).

    Also accepts an optional "`as_note`" parameter, to indicate that output should
    be sent via `Test::More::note()` instead of `Test::More::diag()`.  Difference
    is that a "note" only appears in the verbose TAP stream and does not get shown
    when running under a test harness.

- log\_message(%p)

    Logs the given message.

# AUTHOR

Graham TerMarsch (cpan@howlingfrog.com)

# COPYRIGHT

Copyright (C) 2011, Graham TerMarsch.  All Rights Reserved.

This is free software, you can redistribute it and/or modify it under the
Artistic-2.0 license.

# SEE ALSO

- [Log::Dispatch](https://metacpan.org/pod/Log%3A%3ADispatch)
