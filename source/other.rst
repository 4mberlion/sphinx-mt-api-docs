.. Optimo documentation master file, created by
   sphinx-quickstart on Mon Oct 28 12:18:33 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Dokumentacja Masstrade API
==================================

.. toctree::
   :maxdepth: 2
   :caption: Contents:


Seller's API
============


.. tabs::

   .. tab:: Apples

      .. code-block:: html
         :linenos:

            <h1>code block example</h1>
            <h1>codsse block example</h1>
            <h1>code block example</h1>
            <h1>code block example</h1>

   .. tab:: Pears

      .. literalinclude:: conf.py

   .. tab:: Oranges

      Oranges are orange.

.. code-block:: html
   :linenos:

   <h1>code block example</h1>
   <h1>codsse block example</h1>
   <h1>code block example</h1>
   <h1>code block example</h1>

The audience for this extension are developers and technical writes documenting their RESTful HTTP APIs. This extension has originally been developed for documenting `plone.restapi`_.

.. _sphinxcontrib-httpdomain: https://pythonhosted.org/sphinxcontrib-httpdomain/
.. _plone.restapi: http://plonerestapi.readthedocs.org/

* Configuration:

  The URL scheme, either ``http`` or ``https``, used in the generated examples
  can be configured with the ``httpexample_scheme`` configuration variable. It
  defaults to ``http``.

  ..  code-block:: python

      # conf.py
      httpexample_scheme = 'https'

* Syntax:

  ..  code-block:: rst

      .. http:example:: space separated list of tools
         :request: ../optional/rel/path/to/plaintext/request
         :response: ../optional/rel/path/to/plaintext/response

         Raw plaintext HTTP request example, which is
         required only when :request: is not specified.

 .. jsoncall:: /status

      {"key": ""}

      {
        "serverName": "DevSebaMasstrade_optimo",
        "isProduction": false,
        "remoteWriteEnabled": true,
        "cronEnabled": true,
        "cronExtensionsEnabled": true,
        "adminAccessOnly": true
      }

.. literalinclude:: conf.py

+------------+------------+-----------+
| Method     | URL        | Opis      |
+============+============+===========+
| GET        | column 2   | column 3  |
+------------+------------+-----------+
| POST       | Cells may span columns.|
+------------+------------+-----------+
| body row 3 | Cells may  | - Cells   |
+------------+ span rows. | - contain |
| body row 4 |            | - blocks. |
+------------+------------+-----------+




* Supported tools:

  - curl_
  - wget_
  - httpie_
  - python-requests_

.. _curl: https://curl.haxx.se/
.. _wget: https://www.gnu.org/software/wget/
.. _httpie: https://httpie.org/
.. _python-requests: http://docs.python-requests.org/