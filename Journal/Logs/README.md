<!-- omit in toc -->
# Introduction
To write log messages to journal

<br />

<!-- omit in toc -->
# Table of Contents
- [Fundamental Concepts](#fundamental-concepts)
  - [Log Levels](#log-levels)
- [Packages](#packages)
  - [logging](#logging)
    - [StreamHandler](#streamhandler)
    - [FileHandler](#filehandler)
  - [Loguru](#loguru)
- [Commands](#commands)
  - [logging](#logging-1)
    - [Basic Usage](#basic-usage)
    - [Advanced Usage: use logger to create different frameworks for logging](#advanced-usage-use-logger-to-create-different-frameworks-for-logging)
      - [instantiate logger](#instantiate-logger)
      - [set the threshold for this logger to level](#set-the-threshold-for-this-logger-to-level)
      - [send logs to destinations based on handlers](#send-logs-to-destinations-based-on-handlers)
      - [Example](#example)
      - [Format](#format)
  - [Loguru](#loguru-1)
    - [Basic usage](#basic-usage-1)
    - [Advanced usage](#advanced-usage)
      - [use add to do logging handler, formatter, filter](#use-add-to-do-logging-handler-formatter-filter)
      - [remove handler](#remove-handler)

# Fundamental Concepts

## Log Levels

* debug
* info
* warning: default
* error
* critical


# Packages
## logging
### StreamHandler
* sends logging output to streams such as sys.stdout, sys.stderr or any file-like object

### FileHandler
* sends logging output to a disk file
* inherits the output functionality from **StreamHandler**


## Loguru
* Loguru is much easier than logging

# Commands
## logging

### Basic Usage

    logging.info('info message')
    logging.debug('debug message')

### Advanced Usage: use logger to create different frameworks for logging
#### instantiate logger

    logging.getLogger(name) 

#### set the threshold for this logger to level

    logger.setLevel(logging.DEBUG)

#### send logs to destinations based on handlers

    logger.addHandler(st)

#### Example
* Customize a logger 1

    formatter_1 = logging.Formatter(
        '[%(levelname)1.1s %(asctime)s %(module)s:%(lineno)d] %(message)s',
        datefmt='%Y%m%d %H:%M:%S'
    )
    log_1 = logging.getLogger('test1')
    log_1.setLevel(logging.DEBUG)
    log_1.setFormatter(formatter_1)

* Customize a logger 2

    formatter_2 = logging.Formatter(
        '[%(levelname)1.1s %(asctime)s %(module)s:%(lineno)d] %(message)s',
        datefmt='%Y%m%d %H:%M:%S'
    )
    log_2 = logging.getLogger('test2')
    log_2.setLevel(logging.DEBUG)
    log_2.setFormatter(formatter_2)

* Customize handlers for terminal and files

  * StreamHandler

    st = logging.StreamHandler()
    st.setLevel(logging.CRITICAL)
    st.setFormatter(formatter1)

  * FileHandler

    log_filename = datetime.datetime.now().strftime("%Y-%m-%d_%H_%M_%S.log")
    fl = logging.FileHandler(log_filename)
    fl.setLevel(logging.CRITICAL)
    fl.setFormatter(formatter1)

* add handler to logger. if call logger, logger will send logs to destination

    log_1.addHandler(st)
    log_1.addHandler(fl)
    log_2.addHandler(st)
    
* print logs 

    if __name__ == "__main__":
        log_1.critical('hi')
        log_1.critical('hello')
        log_1.critical('ao')
        log_2.critical('no')

#### [Format](https://docs.python.org/zh-tw/3/library/logging.html#logrecord-attributes)



## Loguru

### Basic usage

    logger.error('error')

### Advanced usage
#### use add to do logging handler, formatter, filter

    test = logger.add(sys.stderr/file_{time}.log/, format="{time} {level} {message}", filter="my_module", level="INFO")

#### remove handler

    logger.remove(test)



    
