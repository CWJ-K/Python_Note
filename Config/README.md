<!-- omit in toc -->
# Introduction
Take note of config

<br />

<!-- omit in toc -->
# Table of Contents
- [Fundamental Concepts](#fundamental-concepts)
  - [ini files](#ini-files)
- [Packages](#packages)
  - [ConfigParser](#configparser)
- [Commands](#commands)
  - [Instantiated Configparser](#instantiated-configparser)
  - [read .ini](#read-ini)
  - [write .ini](#write-ini)
  - [inspect sections of .ini file](#inspect-sections-of-ini-file)

<br />

# Fundamental Concepts
## [ini files](https://docs.python.org/3/library/configparser.html#supported-ini-file-structure)
* the file consists of sections, each of which contains keys with values
  
<br />

# Packages
## ConfigParser
* can read and write .ini files

<br />

# Commands

## Instantiated Configparser
    config = ConfigParser()

## read .ini
    config.read("example.ini")

## write .ini
    with open('example.ini', 'w') as configfile:
    ...   config.write(configfile)

## inspect sections of .ini file 
    config.sections()
