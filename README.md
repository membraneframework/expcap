ExPcap
======

[![hex.pm Custom](https://img.shields.io/badge/expcap-Elixir-brightgreen.svg)](https://hex.pm/packages/expcap)
[![hex.pm Version](https://img.shields.io/hexpm/v/expcap.svg)](https://hex.pm/packages/expcap)
[![hex.pm License](https://img.shields.io/hexpm/l/plug.svg)](https://hex.pm/packages/expcap)

This repository started as fork of [expcap](https://github.com/cobenian/expcap)
Instead of implementing different protocols on our own we use [pkt](https://github.com/msantos/pkt) library written in Erlang.

## Installation

The package can be installed by adding `ex_pcap` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [
    {:ex_pcap, "~> 0.1.0"}
  ]
end
```

## Usage

Here is a sample using mix:

    iex -S mix
    iex> ExPcap.from_file "test/data/dns.cap"

If you want to print the string in a more user friendly format:

    iex -S mix
    iex> "test/data/dns.cap" |> ExPcap.from_file |> String.Chars.to_string	

### Windows

Escript does not run on Windows so the expcap escript will not work. However,
the code in this library should work on Windows if used as an Elixir library.
This has *not* been tested that we are aware of.

## Limitations

* Well formed pcap files can be parsed properly, however corrupted pcap files
may not have helpful error messages.
* Escript will not run on Windows, but the code should.
