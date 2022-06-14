# Perlbrew Bash Completion

Basic tab completion for [perlbrew](https://perlbrew.pl/).

![Shellcheck Action](https://github.com/jonasbn/bash_completion_perlbrew/workflows/Shellcheck%20Action/badge.svg)
![Spellcheck Action](https://github.com/jonasbn/bash_completion_perlbrew/workflows/Spellcheck%20Action/badge.svg)
![Markdownlint Action](https://github.com/jonasbn/bash_completion_perlbrew/workflows/Markdownlint%20Action/badge.svg)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

## Usage

This completion script, executes `perlbrew list` and offers completions for all the `perlbrew` perls and libraries installations you have available.

```bash
$ perlbrew use <tab>
perl-5.10.1
perl-5.20.2
perl-5.20.2@workflow
...
```

And the `bash` completion functionality even assists, when you specify more of your targets

```bash
$ perlbrew use perl-5.20<tab>
perl-5.20.2
perl-5.20.2@workflow
...
```

## Download

```bash
$ curl https://raw.githubusercontent.com/jonasbn/bash_completion_perlbrew/master/perlbrew > perlbrew
```

## Installation

Where your completions are located might vary.

### Personal

If you want to install them for your personal use, do the following.

Create the file: `~/.bash_completion`, containing the code below:

```bash
for bcfile in ~/.bash_completion.d/* ; do
    . $bcfile
done
```

Ref: [ServerFault.com: _Standard place for user defined bash_completion.d scripts?_](https://serverfault.com/questions/506612/standard-place-for-user-defined-bash-completion-d-scripts)

Create a directory for your completions:

```bash
$ mkdir ~/.bash_completion.d
```

Copy your completions into the newly created directory:

```bash
$ cp perlbrew ~/.bash_completion.d/
```

Start a new shell and you should be good to go.

### System-wide example from Debian

Based on [an introduction](https://debian-administration.org/article/316/An_introduction_to_bash_completion_part_1) to `bash` completions on Debian.

```bash
$ sudo cp perlbrew /etc/bash_completion.d/
```

### System-wide example from OSX

This assumes you are using **Homebrew**

Do note that paths vary based on whether you are using `bash` 3 or 4

#### `bash` 3 (Formula: `bash-completions`)

```bash
$ cp perlbrew /usr/local/etc/bash_completion.d/
```

And to activate right away:

```bash
$ source  /usr/local/etc/bash_completion.d/perlbrew
```

#### `bash` 4 (Formula: `bash-completions2`)

```bash
$ cp perlbrew /usr/local/share/bash-completion/completions/
```

And to activate right away:

```bash
$ source /usr/local/share/bash-completion/completions/perlbrew
```

## Motivation

I have a huge list of `perlbrew` library installations and I tend to keep the names long and descriptive, so it seemed like tab completion was an interesting alternative to the _flow breaking copy-pasting_ and error prone typing away.

The programmatic capabilities of `bash` are truly powerful and useful and can be put to good use in use-cases like this.

## See Also

A more elaborate piece of documentation on `bash` completions is available from **The Linux Documentation Project** in the [Advanced Bash-Scripting Guide](http://tldp.org/LDP/abs/html/tabexpansion.html).

From the [GNU Documentation](https://www.gnu.org/software/bash/manual/html_node/Programmable-Completion.html).

Good two-part article, "An Introduction to Bash Completion": [Part 1](https://debian-administration.org/article/316/An_introduction_to_bash_completion_part_1) and [Part 2](https://debian-administration.org/article/317/An_introduction_to_bash_completion_part_2).

Please note that this experimental implementation has only been tested with `bash` version 3.

The most comprehensive collection of `bash` completions I have come across is [the one](https://github.com/scop/bash-completion) from the **Debian Linux distribution**. It is also the one offered for OSX via **Homebrew**.

## License

This is made available under the MIT license, see separate license file.

## Copyright

:copyright: jonasbn 2016-2020
