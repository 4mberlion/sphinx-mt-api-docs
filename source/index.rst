.. Optimo documentation master file, created by
   sphinx-quickstart on Mon Oct 28 12:18:33 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Documentation for Masstrade API
==================================

.. toctree::
   :maxdepth: 2
   :caption: Contents:

Public API
==========

/status
********

**Host:** public-api.masstrade.pl

**Usage:** Retrieves public information of the server. Key is not required for this request. 

.. tabs::

   .. tab:: Playground

      .. jsoncall:: /public-api.masstrade.pl/status

            {}

   .. tab:: Sample response

      .. literalinclude:: public_response/status.json


Seller's API
============

**Host**: seller-api.masstrade.pl

.. raw:: html

    <b>Description:</b> This API is used by seller to connect Masstrade with an ERP system or to make internal integrations.
    The sellers API key is required. Please <a href="mailto:bok@masstrade.pl">contact us</a> to get one.
    <br><br><br>




Metods for Seller
*****************

+------------+------------------------------+--------------------------------------------------------------------------------------+
| **Method** | **URL**                      | **Description**                                                                      |
+------------+------------------------------+--------------------------------------------------------------------------------------+
| GET        | /categories                  | Returns detailed data of MT categories                                               |
+------------+------------------------------+--------------------------------------------------------------------------------------+
| GET        | /channels                    | Returns detailed data of the sales channels (rolo, ebay, allegro etc.)               |
+------------+------------------------------+--------------------------------------------------------------------------------------+
| GET        | /products                    | Returns detailed data of MT products                                                 |
+------------+------------------------------+--------------------------------------------------------------------------------------+
| GET        | /products_translations       | Returns descriptions and titles of MT products with translations                     |
+------------+------------------------------+--------------------------------------------------------------------------------------+
| GET        | /orders                      | Returns detailed data of the order documents                                         |
+------------+------------------------------+--------------------------------------------------------------------------------------+
| GET        | /order/{id}                  | Returns detailed data of an order document with given id                             |
+------------+------------------------------+--------------------------------------------------------------------------------------+
| GET        | /order/{id}/getAttachments   | Returns only an attachment address and file details with given id                    |
+------------+------------------------------+--------------------------------------------------------------------------------------+
| POST       | /order/{id}/addFileAttachment| Uploads an attachment with given id                                                  |
+------------+------------------------------+--------------------------------------------------------------------------------------+
| GET        | /me                          | Returns information of key owner                                                     |
+------------+------------------------------+--------------------------------------------------------------------------------------+
| GET        | /returns                     | Returns detailed data of the documents stored in the Complaints module in Masstrade  |
+------------+------------------------------+--------------------------------------------------------------------------------------+

/categories
***********
+---------------+-------------+---------------------------------------------+
| **Parameter** | **Type**    | **Description**                             |
+---------------+-------------+---------------------------------------------+
| key           | string      | Key generated and saved in Masstrade        |
+---------------+-------------+---------------------------------------------+
| *format*      | string      | Format of the output (**json,** csv, xml)   |
+---------------+-------------+---------------------------------------------+

.. tabs::

   .. tab:: Playground

      .. jsoncall:: /seller-api.masstrade.pl/categories

            {"key": "",
            "format": "json"}

   .. tab:: Sample response: json (default)

      .. literalinclude:: seller_response/categories.json

   .. tab:: Sample response: csv

      .. literalinclude:: seller_response/categories.csv

   .. tab:: Sample response: xml

      .. literalinclude:: seller_response/categories.xml


/channels
*********
+---------------+-------------+---------------------------------------------+
| **Parameter** | **Type**    | **Description**                             |
+---------------+-------------+---------------------------------------------+
| key           | string      | Key generated and saved in Masstrade        |
+---------------+-------------+---------------------------------------------+

.. tabs::

   .. tab:: Playground

      .. jsoncall:: /seller-api.masstrade.pl/channels

            {"key": ""}

   .. tab:: Sample response

      .. literalinclude:: seller_response/channels.json


/products
*********
+---------------+-------------+---------------------------------------------+
| **Parameter** | **Type**    | **Description**                             |
+---------------+-------------+---------------------------------------------+
| key           | string      | Key generated and saved in Masstrade        |
+---------------+-------------+---------------------------------------------+
| *format*      | string      | Format of the output (**json,** csv, xml)   |
+---------------+-------------+---------------------------------------------+

.. tabs::

   .. tab:: Playground

      .. jsoncall:: /seller-api.masstrade.pl/products

            {"key": "",
            "format": "json"}

   .. tab:: Sample response: json (default)

      .. literalinclude:: seller_response/products.json

   .. tab:: Sample response: csv

      .. literalinclude:: seller_response/products.csv

   .. tab:: Sample response: xml

      .. literalinclude:: seller_response/products.xml


/products_translations
**********************
+---------------+-------------+---------------------------------------------+
| **Parameter** | **Type**    | **Description**                             |
+---------------+-------------+---------------------------------------------+
| key           | string      | Key generated and saved in Masstrade        |
+---------------+-------------+---------------------------------------------+
| *format*      | string      | Format of the output (**json,** csv, xml)   |
+---------------+-------------+---------------------------------------------+

.. tabs::

   .. tab:: Playground

      .. jsoncall:: /seller-api.masstrade.pl/products_translations

            {"key": "",
            "format": "json"}

   .. tab:: Sample response: json (default)

      .. literalinclude:: seller_response/products_translations.json

   .. tab:: Sample response: csv

      .. literalinclude:: seller_response/products_translations.csv

   .. tab:: Sample response: xml

      .. literalinclude:: seller_response/products_translations.xml


/orders
*******

+---------------------+-----------------------+------------------------------------------------------------+
| **Parameter**       | **Type**              | **Description**                                            |
+---------------------+-----------------------+------------------------------------------------------------+
| key                 | string                | Key generated and saved in Masstrade                       |
+---------------------+-----------------------+------------------------------------------------------------+
| *outputFormat*      | string                | Format of the output, available formats: api, mt_sync, edi |
+---------------------+-----------------------+------------------------------------------------------------+

.. tabs::

   .. tab:: Playground

      .. jsoncall:: /seller-api.masstrade.pl/orders

            {"key": "",
            "outputFormat": "api"}

   .. tab:: Sample response

      .. literalinclude:: seller_response/orders_all.json

/order/{id}
***********

+---------------------+-----------------------+----------------------------------------------+
| **Parameter**       | **Type**              | **Description**                              |
+---------------------+-----------------------+----------------------------------------------+
| {id}                | int                   | Order id                                     |
+---------------------+-----------------------+----------------------------------------------+
| key                 | string                | Key generated and saved in Masstrade         |
+---------------------+-----------------------+----------------------------------------------+
| *outputFormat*      | string                | Format of the output (**api,** mt_sync, edi) |
+---------------------+-----------------------+----------------------------------------------+

.. tabs::

   .. tab:: Sample response: api (default)

      .. literalinclude:: seller_response/orders_id.json

   .. tab:: Sample response: mt_sync

      .. literalinclude:: seller_response/orders_id_mt_sync.xml

   .. tab:: Sample response: edi

      .. literalinclude:: seller_response/orders_id_edi.xml


/order/{id}/getAttachments
**************************

This request returns only attachments.

+---------------+-------------+---------------------------------------------+
| **Parameter** | **Type**    | **Description**                             |
+---------------+-------------+---------------------------------------------+
| {id}          | int         | Document number                             |
+---------------+-------------+---------------------------------------------+
| key           | string      | Key generated and saved in Masstrade        |
+---------------+-------------+---------------------------------------------+

**Sample response:**

.. literalinclude:: seller_response/order_id_getattachment.json

/order/{id}/addFileAttachment
*****************************

This request replaces the order attachment.

+---------------+-------------+---------------------------------------------+
| **Parameter** | **Type**    | **Description**                             |
+---------------+-------------+---------------------------------------------+
| {id}          | int         | Document number                             |
+---------------+-------------+---------------------------------------------+
| key           | string      | Key generated and saved in Masstrade        |
+---------------+-------------+---------------------------------------------+
| attachmentId  | string/int  | ID assigned to the attachment               |
+---------------+-------------+---------------------------------------------+

**form-data Parameters**

+---------+---------------------+
| **key** | **value**           |
+---------+---------------------+
| file    | {path_to_the_file}  |
+---------+---------------------+
| type    | invoice             |
+---------+---------------------+

The uploaded file should be returned by the */order/{id}/getAttachments* request


/me
***

+---------------+-------------+---------------------------------------------+
| **Parameter** | **Type**    | **Description**                             |
+---------------+-------------+---------------------------------------------+
| key           | string      | Key generated and saved in Masstrade        |
+---------------+-------------+---------------------------------------------+

.. tabs::

   .. tab:: Playground

      .. jsoncall:: /seller-api.masstrade.pl/me

            {"key": ""}

   .. tab:: Sample response

      .. literalinclude:: seller_response/me.json

/channels
*********

+---------------+-------------+---------------------------------------------+
| **Parameter** | **Type**    | **Description**                             |
+---------------+-------------+---------------------------------------------+
| key           | string      | Key generated and saved in Masstrade        |
+---------------+-------------+---------------------------------------------+

.. tabs::

   .. tab:: Playground

      .. jsoncall:: /seller-api.masstrade.pl/channels

            {"key": ""}

   .. tab:: Sample response

      .. literalinclude:: seller_response/channels.json

/returns
********

+--------------+-------------+---------------------------------------------+
| **Parametr** | **Type**    | **Description**                             |
+--------------+-------------+---------------------------------------------+
| key          | string      | Key generated and saved in Masstrade        |
+--------------+-------------+---------------------------------------------+


.. tabs::

   .. tab:: Playground

      .. jsoncall:: /seller-api.masstrade.pl/returns

            {"key": ""}

   .. tab:: Sample response

      .. literalinclude:: seller_response/returns.json
          


