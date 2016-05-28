# Perlbrew Bash Completion

Basic tab completion for [perlbrew](https://perlbrew.pl/).

## Usage

This completion script, executes `perlbrew list` and offers completions for all the `perlbrew` perls and libraries installations you have available.

```
$ perlbrew use <tab>
perl-5.10.1
perl-5.20.2
perl-5.20.2@workflow
...
```

## Installation

```bash
$ curl https://raw.githubusercontent.com/jonasbn/bash_completion_perlbrew/master/perlbrew > perlbrew
```

Where your completions are located might vary:

Based on [an introduction](https://debian-administration.org/article/316/An_introduction_to_bash_completion_part_1) to `bash` completions on Debian.

```bash
$ sudo cp perlbrew /etc/bash_completion.d/
```

This is not a part of [the completions](https://github.com/Homebrew/homebrew-completions) available under `brew` on OSX. But you can copy the `perlbrew` file to the same directory:

```bash
$ cp perlbrew /usr/local/etc/bash_completion.d/
```

And to activate right away:

```bash
$ . /usr/local/etc/bash_completion.d/perlbrew
```

## Motivation

I have a huge list of `perlbrew` library installations and I tend to keep the names long and descriptive, so it seemed like tab completion was an interesting alternative.

The programmatic capabilities of `bash` are truly powerful and useful and can be put to good use in use-cases like this.

## See Also

A more elaborate piece of documentation on `bash` completions is available from **The Linux Documentation Project** in the [Advanced Bash-Scripting Guide](http://tldp.org/LDP/abs/html/tabexpansion.html).

Good two-part article, "An Introduction to Bash Completion": [Part 1](https://debian-administration.org/article/316/An_introduction_to_bash_completion_part_1) and [Part 2](https://debian-administration.org/article/317/An_introduction_to_bash_completion_part_2).

## License

This is made available under the MIT license, see separate license file.

## Copyright 

:copyright: jonasbn 2016
