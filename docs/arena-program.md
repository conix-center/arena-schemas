
Program
=======


ARENA Program

All wire objects have a set of basic attributes ```{object_id, action, type, persist, data}```. The ```data``` attribute defines the object-specific attributes
Program Attributes
------------------

|Attribute|Description|Type|Default|Required|
| :--- | :--- | :--- | :--- | :--- |
|object_id|Object identifier; Must be a valid UUID.|string||Yes|
|action|One of 3 basic Create/Update/Delete actions or a special client event action (e.g. a click)|string; One of: ```['create', 'delete', 'update', 'clientEvent']```|```'create'```|Yes|
|persist|Persist this object in the database|boolean|```true```|Yes|
|type|ARENA program data|string; Must be: ```program```|```'program'```|Yes|
|data|See: [program.md](program.md)|program||Yes|

### Program Data Attributes

|Attribute|Description|Type|Default|Required|
| :--- | :--- | :--- | :--- | :--- |
|name|Name of the program in the format namespace/program-name|string||Yes|
|affinity|Indicates the module affinity (client=client's runtime; none or empty=any suitable/available runtime)|string; One of: ```['client', 'none']```|```'client'```|No|
|instantiate|Single instance of the program (=single), or let every client create a program instance (=client). Per client instance will create new uuid for each program.|string; One of: ```['single', 'client']```|```'client'```|Yes|
|filename|Filename of the entry binary|string||Yes|
|filetype|Type of the program (WA=WASM or PY=Python)|string; One of: ```['WA', 'PY']```|```'['WA']'```|Yes|
|args|Command-line arguments (passed in argv). Supports variables: ${scene}, ${mqtth}, ${cameraid}, ${username}, ${runtimeid}, ${moduleid}, ${query-string-key}|array||No|
|env|Environment variables. Supports variables: ${scene}, ${mqtth}, ${cameraid}, ${username}, ${runtimeid}, ${moduleid}, ${query-string-key}|array|```['MID=${moduleid}', 'SCENE=${scene}', 'MQTTH=${mqtth}', 'REALM=realm']```|Yes|
|channels|Channels describe files representing access to IO from pubsub and client sockets (possibly more in the future; currently only supported for WASM programs).|array|```[{'path': '/ch/${scene}', 'type': 'pubsub', 'mode': 'rw', 'params': {'topic': 'realm/s/${scene}'}}]```|No|
