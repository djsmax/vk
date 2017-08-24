=========================
vk.com API Python wrapper
=========================

This is a vk.com (the largest Russian social network)
python API wrapper. The goal is to support all API methods (current and future)
that can be accessed from server. This version improves nohttps signature calculating.

Quickstart
==========

Install
-------

.. code:: bash

    git clone https://github.com/djsmax/vk.git
    cd vk
    python setup.py install

Usage
-----

.. code:: python

    >>> import vk
    >>> api = vk.API(v = '5.68')
    >>> api.users.get(user_ids=1)
    [{'first_name': 'Pavel', 'last_name': 'Durov', 'id': 1}]
	
Usage with signature
--------------------

This can be usable in cases where token has a 'nohttps' scope - then for each API request signature calculation is necessary.

.. code:: python

    >>> import vk
	>>> token = '0000000000000000000000000000000000000000000000000000000000000000000000000000000000000' # your vk token
	>>> secret = '0000000000000000' # your vk app secret
    >>> api = vk.API(access_token = token, nohttps_secret = secret, v = '5.68')
    >>> api.users.get(user_ids=1) ## now for all api requests signature will be calculated
    [{'first_name': 'Pavel', 'last_name': 'Durov', 'id': 1}]
	


See https://vk.com/dev/methods for detailed API guide.

More info
=========

`Read full documentation <http://vk.readthedocs.org>`_
