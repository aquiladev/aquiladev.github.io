# Tree in Solidity
[Tree](https://en.wikipedia.org/wiki/Tree_(data_structure)) is a widely used abstract data type, you can imagine structure of hierarchical organization, file system, etc.

![image]

Regular approach to define the structure is using `node`. Access to node can be done via `path`.
The structure should have a way to manage nodes and easily retrieve nodes in both directions.

### Path
Path is access key of node. It is important piece in the structure,
coz we would like to store nodes in a simple data type for low complexity and memory optimization.

| Node | Name | Parent | Path |
|---|---|---|---|
| Node0 | Alpha | - | Alpha |
| Node0-0 | Bravo | Alpha | Alpha/Bravo |
| Node0-1 | Charlie | Alpha | Alpha/Charlie |
| Node0-2 | Delta | Alpha | Alpha/Delta |
| Node0-1-0 | Echo | Alpha/Charlie | Alpha/Charlie/Echo |

`Node0` is root of the structure, it has linked nodes [`Node0-0`, `Node0-1`, `Node0-2`] and second node `Node0-1` has linked node `Node0-1-0`

### Node
Node is item in the structure.

```
struct Node {
    bytes32 name;       // name of node
    bytes32 parent;     // parent node's path
    bytes32 data;       // node's data
    bytes32[] nodes;    // list of linked nodes' paths
}
```
There is one root node and linked sub-nodes it the structure.

### Specification
In a nutshell we need to define operations which we can do nodes: add, update, remove and read.
```
mapping(bytes32 => Node) nodes;

function get(bytes32 _name, bytes32 _parent) public view returns (bytes32, bytes32, bytes32, bytes32[]) {
    Node storage node = nodes[keccak256(_parent, _name)];
    return (node.name, node.parent, node.data, node.nodes);
}
    
function add(bytes32 _name, bytes32 _parent, bytes32 _data) public {
    require(_name.length > 0);

    bytes32 path = keccak256(_parent, _name);
    nodes[path] = Node({
        name: _name, 
        parent: _parent, 
        data: _data, 
        nodes: new bytes32[](0)
    });
    nodes[_parent].nodes.push(path);
}

function update(bytes32 _name, bytes32 _parent, bytes32 _data) public {
    bytes32 path = keccak256(_parent, _name);
    Node storage node = nodes[path];

    node.data = _data;
}

function remove(bytes32 _name, bytes32 _parent) public {
    bytes32 path = keccak256(_parent, _name);
    require(nodes[path].nodes.length == 0);                 // allow to remove leaves (node without linked nodes)

    delete nodes[path];                                     // removes from nodes
    
    // removes from parent list of nodes
    bytes32[] storage childs = nodes[_parent].nodes;
    for (uint256 i = getIndex(childs, path); i < childs.length - 1; i++) {
        childs[i] = childs[i + 1];
    }
    delete childs[childs.length - 1];
    childs.length--;
}

function getIndex(bytes32[] childs, bytes32 _path) pure internal returns (uint256) {
    for (uint256 i = 0; i < childs.length; i++) {
        if (_path == childs[i]) {
            return i;
        }
    }
    return childs.length - 1;
}
```

`remove` function is quite gas consuming operation, coz we define links between nodes in both directions,
but it is not fully necessary to have two-direction links, we can avoid storing links to sub-nodes,
in the case entire structure should be stored in memory of client before surfing.

Tags: Ethereum, Blockchain, Solidity, Solidity 0.4.15
