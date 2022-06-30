<!-- omit in toc -->
# Introduction
Write log messages in journal.

<br />

<!-- omit in toc -->
# Table of Contents
- [Fundamental Concepts](#fundamental-concepts)
  - [1. Log Levels](#1-log-levels)
- [Packages](#packages)
  - [1. logging](#1-logging)
    - [1.1. StreamHandler](#11-streamhandler)
    - [1.2. FileHandler](#12-filehandler)
  - [2. Loguru](#2-loguru)
- [Commands](#commands)
  - [1. logging](#1-logging-1)
    - [1.1. Basic Usage](#11-basic-usage)
    - [1.2. Advanced Usage: use logger to create different frameworks for logging](#12-advanced-usage-use-logger-to-create-different-frameworks-for-logging)
      - [1.2.1. instantiate logger](#121-instantiate-logger)
      - [1.2.2. set the threshold for this logger to level](#122-set-the-threshold-for-this-logger-to-level)
      - [1.2.3. send logs to destinations based on handlers](#123-send-logs-to-destinations-based-on-handlers)
      - [1.2.4. Example](#124-example)
      - [1.2.5. Format](#125-format)
  - [2. Loguru](#2-loguru-1)
    - [2.1. Basic usage](#21-basic-usage)
    - [2.2. Advanced usage](#22-advanced-usage)
      - [2.2.1. use add to do logging handler, formatter, filter](#221-use-add-to-do-logging-handler-formatter-filter)
      - [2.2.2. remove handler](#222-remove-handler)

<br />

# Fundamental Concepts

## 1. Log Levels
* debug
* info
* warning: default
* error
* critical

<br />

# Packages

## 1. logging

### 1.1. StreamHandler
* sends logging output to streams such as sys.stdout, sys.stderr or any file-like object

<br />

### 1.2. FileHandler
* sends logging output to a disk file
* inherits the output functionality from **StreamHandler**

<br />

## 2. Loguru
* Loguru is much easier than logging

<br />

# Commands

<br />

## 1. logging

### 1.1. Basic Usage

  ```python
  logging.info('info message')
  logging.debug('debug message')

  ```

<br />

### 1.2. Advanced Usage: use logger to create different frameworks for logging

#### 1.2.1. instantiate logger

  ```python
  logging.getLogger(name) 
  ```

<br />

#### 1.2.2. set the threshold for this logger to level

  ```python
  logger.setLevel(logging.DEBUG)
  ```

<br />

#### 1.2.3. send logs to destinations based on handlers

  ```python
  logger.addHandler(st)
  ```

<br />

#### 1.2.4. Example
* Customize a logger 1

  ```python
  formatter_1 = logging.Formatter(
      '[%(levelname)1.1s %(asctime)s %(module)s:%(lineno)d] %(message)s',
      datefmt='%Y%m%d %H:%M:%S'
  )
  log_1 = logging.getLogger('test1')
  log_1.setLevel(logging.DEBUG)
  log_1.setFormatter(formatter_1)
  ```

* Customize a logger 2

  ```python
  formatter_2 = logging.Formatter(
      '[%(levelname)1.1s %(asctime)s %(module)s:%(lineno)d] %(message)s',
      datefmt='%Y%m%d %H:%M:%S'
  )
  log_2 = logging.getLogger('test2')
  log_2.setLevel(logging.DEBUG)
  log_2.setFormatter(formatter_2)
  ```

* Customize handlers for terminal and files

  * StreamHandler

    ```python
    st = logging.StreamHandler()
    st.setLevel(logging.CRITICAL)
    st.setFormatter(formatter1)
    ```

  * FileHandler

    ```python
    log_filename = datetime.datetime.now().strftime("%Y-%m-%d_%H_%M_%S.log")
    fl = logging.FileHandler(log_filename)
    fl.setLevel(logging.CRITICAL)
    fl.setFormatter(formatter1)
    ```

* add handler to logger. if call logger, logger will send logs to destination

  ```python
  log_1.addHandler(st)
  log_1.addHandler(fl)
  log_2.addHandler(st)
  ```
    
* print logs 

  ```python
  if __name__ == "__main__":
      log_1.critical('hi')
      log_1.critical('hello')
      log_1.critical('ao')
      log_2.critical('no')
  ```

<br />

#### 1.2.5. [Format](https://docs.python.org/zh-tw/3/library/logging.html#logrecord-attributes)

<br />

## 2. Loguru

### 2.1. Basic usage

  ```python
  logger.error('error')
  ```

<br />

### 2.2. Advanced usage

#### 2.2.1. use add to do logging handler, formatter, filter

  ```python
  test = logger.add(sys.stderr/file_{time}.log/, format="{time} {level} {message}", filter="my_module", level="INFO")
  ```

<br />

#### 2.2.2. remove handler

  ```python
  logger.remove(test)
  ```



    
