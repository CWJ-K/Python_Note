<!-- omit in toc -->
# Introduction
Take note of methods to read files
<br />

<!-- omit in toc -->
# Table of Contents
- [Fundamental Concepts](#fundamental-concepts)
  - [Text Streams](#text-streams)
  - [Binary Streams](#binary-streams)
- [Package](#package)
  - [io (input/output)](#io-inputoutput)
    - [StringIO](#stringio)
- [seek](#seek)
- [why use bytesio](#why-use-bytesio)

<br />

# Fundamental Concepts
## Text Streams
* contains printable characters and control characters that are organized into lines. Each line consists of zero or more characters and ends with a new-line character (\n)
## Binary Streams
* contains a sequence of bytes
  * e.g. 01010002

<br />

# Package
## io (input/output)
* deals with various types of I/O
* three main types
  * text I/O
  * binary I/O
  * raw I/O

### StringIO
* In-memory text streams
* inherits TextIOBase
* When to use? <br /> In cases where you want a file-like object that ACTS like a file, but is writing to an in-memory string buffer

        df = pd.read_csv(
            io.StringIO(response.content.decode("big5")),
            index_col=False
        )


# seek
https://stackoverflow.com/questions/26879981/writing-then-reading-in-memory-bytes-bytesio-gives-a-blank-result




# why use bytesio
https://www.confessionsofadataguy.com/you-have-to-try-this-from-io-import-stringio-bytesio/

also binary data has good performance