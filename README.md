node-red-node-cf-cloudant
=========================
A set of [Node-RED](https://nodered.org) nodes to work with documents
in a [Cloudant](https://cloudant.com) database that is integrated with
[IBM Cloud](https://cloud.ibm.com).

Install
-------
Ideally, install from the palette manager inside Node-RED.

Alternatively, install from [npm](http://npmjs.org)
```
npm install node-red-node-cf-cloudant
```

Usage
-----
Allows basic access to a [Cloudant](https://cloudant.com) database to
`insert`, `update`, `delete` and `search` for documents. Also `bulk`
operation is supported.

To **insert** a new document into the database you have the option to store
the entire `msg` object or just the `msg.payload`. If the input value is not
in JSON format, it will be transformed before being stored. If `msg` is an array,
all elements will be processed using the **bulk operations API**.

For **update** and **delete**, you must pass the `_id` and the `_rev`as part
of the input `msg` object. **Bulk operations** are also supported when putting documents as
an array in the input `msg` object.

To **search** for a document you have three options:
* get a document directly by its `_id`
* use [query](https://cloud.ibm.com/docs/Cloudant?topic=Cloudant-query)
* use an existing [search index](https://cloud.ibm.com/docs/Cloudant?topic=Cloudant-search#queries)
from the database
* use an existing [view](https://cloud.ibm.com/docs/Cloudant?topic=Cloudant-using-views)

When getting documents by id, the `payload` will be the desired `_id` value.

For `query`, the `payload` will be the set to an object with a [declarative JSON query syntax](https://cloud.ibm.com/docs/Cloudant?topic=Cloudant-query).

For `search indexes`, the query should follow the format `indexName:value`.

For `views`, `payload` should be set be set to an object containing key/value pairs
as defined in the Query string section in the [Cloudant documentation](https://cloud.ibm.com/docs/Cloudant?topic=Cloudant-using-views)

Authors
-------
* Adam Hammond

Based on the node written and enhanced by:
* Austin Chang
* Luiz Gustavo Ferraz Aoqui
* Túlio Pascoal
