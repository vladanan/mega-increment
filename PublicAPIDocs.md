# Mega increment API core functions - MACf
# Public API Documentation


## Does this API cover all functionalities as GUI for Advanced options in VSCode Mega increment extension?

- Some of the functionalities are tied to specifics of working space at VSCode editor or GUI Advanced version. But, all text processing available at extension is also available from this MACf API.

- For details please check Readme.md for extension and Change log.



## Simple example for curl on Linux:

In string `Some sample text with number 200.` number **200** is incremented with **1**.

    curl -X POST -H 'accept: text/html' 'https://vezbamo3.vercel.app/api/mi/v1' -d 'data={"lineText":"Some sample text with number 200.","incr":"5","parts":[{"selectionType":"number","timeStamp":"2024-01-18T23:34:18.293Z","stepping":1,"indexOf":29,"partText":"200"}]}'

Beautified:

    curl -X POST -H 'accept: text/html' 'https://vezbamo3.vercel.app/api/mi/v1' -d 'data=
    {
        "lineText": "Some sample text with number 200.",
        "incr": "5",
        "parts": [
            {
                "selectionType": "number",
                "timeStamp": "2024-01-18T23:34:18.293Z",
                "stepping": 1,
                "indexOf": 29,
                "partText": "200"
            }
        ]
    }'

Result from API:  

Some sample text with number **201**.  
Some sample text with number **202**.  
Some sample text with number **203**.  
Some sample text with number **204**.

- **Be careful when using `'` and `"` in curl API calls from (Linux/Mac) shell(s). Because of shell performing string concatenation on the command line and JSON format which depends on `""` you probably must:**
    + escape each `'` with `'\''` for shell concatenation
    + escape each `"` with `\"` for JSON parsing.
- **In some programming languages practical implementation for escaping like this might require additional escaping of backslash `\` character so it might look as this: `'\\''` and `\\"`.**



## HTTPS request:

In string `Some sample text with number 200.` number **200** is **incremented with -3** i.e. **decremented with 3**.

    https://vezbamo3.vercel.app/api/mi/v1?data={"lineText":"Some sample text with number 200.","incr":"5","parts":[{"selectionType":"number","timeStamp":"2024-01-18T23:34:18.293Z","stepping":-3,"indexOf":29,"partText":"200"}]}

Beautified:

    https://vezbamo3.vercel.app/api/mi/v1?data=
    {
        "lineText": "Some sample text with number 200.",
        "incr": "5",
        "parts": [
            {
                "selectionType": "number",
                "timeStamp": "2024-01-18T23:34:18.293Z",
                "stepping": -3,
                "indexOf": 29,
                "partText": "200"
            }
        ]
    }'


Result:  

Some sample text with number **197**.  
Some sample text with number **194**.  
Some sample text with number **191**.  
Some sample text with number **188**.  
Some sample text with number **185**.

- **Be carefull when sending HTTPS request with JSON data. If you have special charachters in your meesage like `\` , `@` , `&` , `#` etc. you may need to first convert them into their respective HEX value (`#` \u0023, `&` \u0026, `\` \u005C, `@` \u0040 etc.) and then send your message. Also remember to escape `"` with `\"`.**
- For other hex values see: https://en.wikipedia.org/wiki/List_of_Unicode_characters .



## Basic curl structure with simple char set, number and enum:

In string `Some sample text with abc, number 200 and enum for color red.` part **abc** is incremented with +1 for each separate character, number **200** is incremented with -3 (i.e. decremented by 3), enum **red** for colors is incremented by +1. Incrementation is performed 9 times.

    curl -X POST -H 'accept: text/html' 'https://vezbamo3.vercel.app/api/mi/v1' -d 'data={"lineText": "Some sample text with abc, number 200 and enum for color red.","incr": "9","parts": [{"selectionType": "simple","timeStamp": "2024-01-18T23:43:45.430Z","stepping": 1,"indexOf": 22,"partText": "abc"},{"selectionType": "number","timeStamp": "2024-01-18T23:43:52.537Z","stepping": "-3","indexOf": 34,"partText": "200"},{"selectionType": "enum","enumArray": ["red","green","blue","cyan","magenta","yellow","black"],"enumVariant": "continuous","timeStamp": "2024-01-18T23:44:03.992Z","stepping": 1,"indexOf": 57,"partText": "red"}]}'

Beautified:

    curl -X POST -H 'accept: text/html' 'https://vezbamo3.vercel.app/api/mi/v1' -d 'data=
    {
    "lineText": "Some sample text with abc, number 200 and enum for color red.",
    "incr": "9",
    "parts": [
        {
            "selectionType": "simple",
            "timeStamp": "2024-01-18T23:43:45.430Z",
            "stepping": 1,
            "indexOf": 22,
            "partText": "abc"
        },
        {
            "selectionType": "number",
            "timeStamp": "2024-01-18T23:43:52.537Z",
            "stepping": "-3",
            "indexOf": 34,
            "partText": "200"
        },
        {
            "selectionType": "enum",
            "enumArray": [
                "red",
                "green",
                "blue",
                "cyan",
                "magenta",
                "yellow",
                "black"
            ],
            "enumVariant": "continuous",
            "timeStamp": "2024-01-18T23:44:03.992Z",
            "stepping": 1,
            "indexOf": 57,
            "partText": "red"
        }
    ]
}'

Result:  

Some sample text with **bcd**, number **197** and enum for color **green**.  
Some sample text with **cde**, number **194** and enum for color **blue**.  
Some sample text with **def**, number **191** and enum for color **cyan**.  
Some sample text with **efg**, number **188** and enum for color **magenta**.  
Some sample text with **fgh**, number **185** and enum for color **yellow**.  
Some sample text with **ghi**, number **182** and enum for color **black**.  
Some sample text with **hij**, number **179** and enum for color **red**.  
Some sample text with **ijk**, number **176** and enum for color **green**.  
Some sample text with **jkl**, number **173** and enum for color **blue**.



## Part object examples for date, time, hex, binary, random, crypto:
*Hex and binary are only tested for positive numbers.*

    https://vezbamo3.vercel.app/api/mi/v1?data={"lineText":"Sample 2024-01-21 22:59:33 abc 1101 anything 7593401834823851","incr":"12","parts":[{"selectionType":"YYYY-MM-DD","timeStamp":"2024-01-21T22:07:07.434Z","stepping":3,"indexOf":7,"partText":"2024-01-21"},{"selectionType":"hh:mm:ss","timeStamp":"2024-01-21T22:07:10.254Z","stepping":3,"indexOf":18,"partText":"22:59:33"},{"selectionType":"hex","timeStamp":"2024-01-21T22:07:14.600Z","stepping":3,"indexOf":27,"partText":"abc"},{"selectionType":"binary","timeStamp":"2024-01-21T22:07:18.951Z","stepping":3,"indexOf":31,"partText":"1101"},{"selectionType":"random","timeStamp":"2024-01-21T22:07:21.803Z","stepping":0,"indexOf":36,"partText":"anything"},{"selectionType":"crypto","timeStamp":"2024-01-21T22:07:56.657Z","stepping":0,"indexOf":45,"partText":"7593401834823851"}]}

Beautified:  

    https://vezbamo3.vercel.app/api/mi/v1?data=
    {
        "lineText": "Sample 2024-01-21 22:59:33 abc 1101 anything 7593401834823851",
        "incr": "12",
        "parts": [
            {
            "selectionType": "YYYY-MM-DD",
            "timeStamp": "2024-01-21T22:07:07.434Z",
            "stepping": 3,
            "indexOf": 7,
            "partText": "2024-01-21"
            },
            {
            "selectionType": "hh:mm:ss",
            "timeStamp": "2024-01-21T22:07:10.254Z",
            "stepping": 3,
            "indexOf": 18,
            "partText": "22:59:33"
            },
            {
            "selectionType": "hex",
            "timeStamp": "2024-01-21T22:07:14.600Z",
            "stepping": 3,
            "indexOf": 27,
            "partText": "abc"
            },
            {
            "selectionType": "binary",
            "timeStamp": "2024-01-21T22:07:18.951Z",
            "stepping": 3,
            "indexOf": 31,
            "partText": "1101"
            },
            {
            "selectionType": "random",
            "timeStamp": "2024-01-21T22:07:21.803Z",
            "stepping": 0,
            "indexOf": 36,
            "partText": "anything"
            },
            {
            "selectionType": "crypto",
            "timeStamp": "2024-01-21T22:07:56.657Z",
            "stepping": 0,
            "indexOf": 45,
            "partText": "7593401834823851"
            }
        ]
    }

Result:  

    Sample 2024-01-24 22:59:36 abf 10000 RD.P$pB. 3637343802  
    Sample 2024-01-27 22:59:39 ac2 10011 ?F+H'AC) 1760623159  
    Sample 2024-01-30 22:59:42 ac5 10110 iG^T]*s< 2131447025  
    Sample 2024-02-02 22:59:45 ac8 11001 B.j_r]_y 1359429649  
    Sample 2024-02-05 22:59:48 acb 11100 O|0:TKq8 1664548742  
    Sample 2024-02-08 22:59:51 ace 11111 V&%g'rhU 1460352170  
    Sample 2024-02-11 22:59:54 ad1 100010 o@{BtsaO 2372504937  
    Sample 2024-02-14 22:59:57 ad4 100101 d#g|{-yg 3297747867  
    Sample 2024-02-17 23:00:00 ad7 101000 %(H+Zyel 3845720973  
    Sample 2024-02-20 23:00:03 ada 101011 Zpu.UDu- 1257714998  
    Sample 2024-02-23 23:00:06 add 101110 6'PkcA93 3450268136  
    Sample 2024-02-26 23:00:09 ae0 110001 J.ic8@0! 248079222  


## Types for data section keys (*all are required*)

- **lineText**: `string` which contains text whom some parts will be incremented. Can be multi line.

- **incr**: `number` positive **integer**, indicates how many times various partText strings should be incremented.

- **parts**: `array` which contains `objects` with data about selected text parts for incrementation.

- **selectionType**: `string` from array: ['simple', 'number', 'enum', 'YYYY-MM-DD', 'YYYY-MM', 'MM-DD', 'hh:mm:ss', 'hh:mm', 'mm:ss', 'hex', 'binary', 'random', 'crypto']. Tells API how to treat partText.  
**Choosing incompatible type for partText i.e. number for pure alphabetic string or binary for hex number might produce unexpected result. At present API is `not` checking for this (in)compatibility.**

    + **number**: positive, zero, negative, integer or floating point
        * If you use floating point stepping on integer numbers without decimal point i.e. inputting stepping of 0.333333 on 2 then 2 will not turn in to floating point 2.0 but instead it will go in `fractional stepping` and be incremented every third time. For example: if you input stepping of 0.25 increment will occur every fourth time, for 0.2 every fifth and so on.
        * Numbers with floating point are recognized by decimal point, so if you want 5 to be incremented by 0.2 you should write it as 5.0.
        * Both integers and floating point numbers support leading zeros.

    + **enum**: predefined JSON array i.e. ["apple","penguin","window","posix"] which must exist in `enumArray`. It supports `fractional stepping`.

    + **YYYY-MM-DD, YYYY-MM, MM-DD**: date parts from ISO full date string. They support `fractional stepping`.

    + **hh:mm:ss, hh:mm, mm:ss**: time parts without millisecond from ISO full date string. They support `fractional stepping`.

    + **simple**: any string whom individual characters will be incremented by ASCII order i.e.: abcd, bcde, cdef, defg...  It supports `fractional stepping`.

    + **hex**: hexadecimal string which is incremented in same fashion as decimal number. Supports leading zeros.

    + **binary**: binary string which is incremented in same fashion as decimal number. Supports leading zeros.

    + **crypto**: integer which will be followed by cryptographically safe array of numbers. Any integer can be selected but result numbers will be in 8/16/32/64bit format depending (not precisely) on number of digits in selected number.

    + **random**: any string which will be followed by random printable ASCII characters, not cryptographically safe format.


- **timeStamp**: ISO date `string` or any string consisting of characters used in ISO date (regex: `/[^0-9TZ\-:\.]+/g`). Examples: 1, 2, 3, 2024-12, 12:54, T1, Z2, -1.2, 5:-Z or similar strings. Used for differentiation amongst parts which may have same partText (and same selectionType).

- **stepping**: `number` positive, negative or zero. Used to calculate incrementation. Example: 1, 2, 3, 4 is stepping 1; 10, 8, 6, 4 is stepping -2; 5.1, 5.3, 5.4 is stepping 0.2.
    + For crypto and random selectionType stepping is irrelevant.
    + Choosing floating point stepping on selectionType `simple`, integer `number` without decimal point, `enum`, `date` and `time` will trigger `fractional stepping` mode. If stepping is 0.333333 they will be incremented every third time. If you input stepping of 0.25 increment will occur every fourth time, for 0.2 every fifth and so on.
    + Numbers with floating point are recognized by decimal point, so if you want 5 to be incremented by 0.2 you should write it as 5.0.

- **indexOf**: `number` positive **integer** or **zero**. Indicates position of partText in lineText. Positions are `zero-based` index numbers.

- **partText**: `string` contains selected part of lineText which should be incremented according to selectionType and stepping.

- *Specifics for enums:*

- **enumArray**: JSON array i.e. ["sun","mon","tue","wen","thu","fri","sat"] wich will be used for incrementing through its items.

- **enumVariant**: `string` from array: [continuous, ranged]. Tells API how to treat list from enumArray during incrementations:
    + **continuous**: treats enum list as continuous i.e. infinite and increments items in linear fashion. When incrementation reaches the end of list it goes further like there is new list attached. If we increment enum with simple numbers ["one","two","three","four","five","six","seven","eight","nine","ten"] starting from `one` and with stepping 3 we will have: `one`, `four`, `seven`, `ten` *and then:* `three` (lite thirteen), `six` (like sixteen), `nine` (like nineteen) etc. etc.
    + **ranged**: enum list is contained in its range so increments beyond list length are trimmed. This variant makes sense if you start from the beginning or middle of the enum but if you start from near the end it makes less sense:
        * Let's say we start from `six` with stepping 3 in numbers. After 2 increments it goes out of the enum range because `six` + 3 = `nine` and +3 = `twelve`:
            - but we can't go to `twelve` or `two` because we selected ranged variant so `two` and the rest will be trimmed 
            - and we also can't go to `one` because it is not the starting position and it also doesn't fit for decrement: `six` -3 = `three` and -3 = `zero`, so `one` is not solution.
        * So in this case  and only 2 items from enum will be repeated constantly in result: `six` and `nine`.
        * Therefore, ranged is very specific and you must clearly understand how it behaves in order to use it correctly in relation to continuous. Best is to first test result with your expectations.


## Licence
Copyright (C) Vladan Anđelković. All rights reserved.
