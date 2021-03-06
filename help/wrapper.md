
∴ rvm wrapper <ruby_string> [<wrapper_prefix>|--no-prefix] [binary[ binaries[ ...]]]

where ruby_string is the ruby version and gemset combination to wrap
(it can also refer to a valid project path), wrapper_prefix is what to
prepend to the name of the generated wrapper, and binary and binaries
are the names of the binaries for which you wish to provide a wrapper
(e.g. gem).

When no binaries are provided, rvm will (by default) generate wrappers for
ruby, gem, rake, irb, rdoc, ri, and testrb.

Examples:

If you wish to provide an environment-specific wrapper for rspec with a
rails 3 gemset, you could do:

  ∴ rvm --create ree@rails3
  ∴ rvm wrapper ree@rails3 r3 spec

Which would add r3_spec with the specified environment to the bin
directory where you installed rvm.

Alternatively, if you do:

  ∴ rvm wrapper ruby-1.9.2-head

It will create binaries named ruby, gem, rake, irb, rdoc, ri and tesrb
in the rvm bin directory.

Finally, to show another real and common use, you can use wrapper
to generate ruby executables and gems for passenger to use. Namely:

  ∴ rvm use ree@rails3 --passenger

is equivelant to:

  ∴ rvm use ree@rails3
  ∴ rvm wrapper ree@rails3 passenger

Which creates passenger_* binaries in the rvm bin directory using
ree and the rails3 gemset.
