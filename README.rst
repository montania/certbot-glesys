GleSYS DNS Authenticator for Certbot
====================================
This allows automatic completion of `Certbot's <https://github.com/certbot/certbot>`_
DNS01 challange for domains managed on `GleSYS <https://www.glesys.com/>`_ DNS.


Installing
----------
.. code-block::

   $ pip install certbot-glesys


Usage
-----
Create an API key with the following permissions:

- ``domain:listrecords``
- ``domain:addrecord``
- ``domain:deleterecord``

Don't forget to give access to the appropriate IP-address range. If you wan't
to be able to run the client from anywhere, enter ``0.0.0.0/0``.

To use the authenticator you need to provide some required options:

``--certbot-glesys:auth-credentials`` *(required)*
  INI file with ``user`` and ``password`` for your GlesSYS API user.

The credentials file must have the following format:

.. code-block::

   certbot_glesys:auth_user = CL00000
   certbot_glesys:auth_password = apikeygoeshere

For safety reasons the file must not be world readable. You can solve this by
running:

.. code-block::

   $ chmod 600 credentials.ini


Disclaimer
----------
This plugin is neither affiliated with nor endorsed by GleSYS Internet Services
AB.
