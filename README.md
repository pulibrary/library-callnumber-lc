Library-Callnumber-LC
=====================

DESCRIPTION
-----------

callnumber is a Python library for working with Library of Congress call 
numbers.  It helps with normalizing Library of Congress call numbers and
creating ranges of normalized call numbers. 


INSTALLATION
------------

(OPTIONAL) Run the test suite to make sure things are working:

    python test.py

To install this module, run the following commands:

    python setup.py install


USAGE
-----

First import the module:

    >>> import callnumber

Create an LC callnumber object, print out some properties:

    >>> lccn = callnumber.LC('HE 8700.7 p6 t44 1983')
    >>> lccn.denormalized
    'HE 8700.7 p6 t44 1983'
    >>> lccn.normalized
    'HE 870070P600T440 000 1983'
    >>> lccn.components()
    ['HE', '8700.7', '.P6', 'T44', '1983']
    >>> lccn.components(include_blanks=True)
    ['HE', '8700.7', '.P6', 'T44', '', '1983']

Inspect the range associated with a callnumber

    >>> lccn = callnumber.LC('HE8700.7')
    >>> lccn.range_start
    'HE 870070'
    >>> lccn.range_end
    'HE 870079~999~999~999'

Normalization is also provided as a module method for the simplest use cases:

    >>> callnumber.normalize('A 123.4 .c11')
    'A  012340C110'
    >>> callnumber.normalize('B11 .c13 .d11')
    'B  001100C130D110'


LICENSE
-------

MIT


COPYRIGHT
---------

Copyright (C) 2009 Michael J. Giarlo <leftwing@alumni.rutgers.edu>
