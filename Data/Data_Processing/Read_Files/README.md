<!-- omit in toc -->
# Introduction
(WIP)
How to use I/O when reading files?

<br />

<!-- omit in toc -->
# Table of Contents
- [Fundamental Concepts](#fundamental-concepts)
  - [1. Text Streams](#1-text-streams)
  - [2. Binary Streams](#2-binary-streams)
- [Package](#package)
  - [1. io (input/output)](#1-io-inputoutput)
    - [1.1. StringIO](#11-stringio)
- [seek](#seek)
- [why use bytesio](#why-use-bytesio)

<br />

# Fundamental Concepts

## 1. Text Streams
* contains printable characters and control characters that are organized into lines. Each line consists of zero or more characters and ends with a new-line character (\n)

<br />

## 2. Binary Streams
* contains a sequence of bytes
  * e.g. 01010002

<br />

# Package

## 1. io (input/output)
* deals with various types of I/O
* three main types
  * text I/O
  * binary I/O
  * raw I/O

<br />

### 1.1. StringIO
* In-memory text streams
* inherits TextIOBase
* When to use? <br /> In cases where you want a file-like object that ACTS like a file, but is writing to an in-memory string buffer

  ```python
  df = pd.read_csv(
      io.StringIO(response.content.decode("big5")),
      index_col=False
  )
  ```

<br />

# seek
https://stackoverflow.com/questions/26879981/writing-then-reading-in-memory-bytes-bytesio-gives-a-blank-result


<br />

# why use bytesio
https://www.confessionsofadataguy.com/you-have-to-try-this-from-io-import-stringio-bytesio/

also binary data has good performance