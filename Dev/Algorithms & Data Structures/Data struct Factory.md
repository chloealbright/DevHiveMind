![[unnamed (32).gif]]

A data structure is a structure which organizes certain data in a certain way. You can implement structures in ways different that by using classes (that's what you do in languages which don't support OOP e.g.; you can still implement a data structure in C let's say).

class ListNode {  
constructor(value = null) {  
this.value = value;  
[this.next](http://this.next/) = null;  
}  
}  
  
class DoubleLLNode {  
constructor(value) {  
this.head = {  
value: value,  
next: null,  
prev: null  
};  
this.tail = this.head;  
// this.length = 1;  
}  
}  
  
  
class TreeNode {  
constructor(value){  
this.value = value;  
this.left = null;  
this.right = null;  
}  
}  
  
  
class Vertex {  
constructor(id) {  
[this.id](http://this.id/) = id !== undefined ? id : null;  
this.edges = [];  
}  
}  
  
class NodeConstructor {  
  
ArrayLinkListDeserialize(arr) {  
if (arr.length === 0) { return null; }  
let head = new ListNode(arr[0]);  
let current = head;  
for (let i = 1; i < arr.length; i++) {  
[current.next](http://current.next/) = new ListNode(arr[i]);  
current = current.next;  
// see if works with leetcode Question  
[if(current.next](http://if%28current.next/) === null){  
[current.next](http://current.next/) = null;  
}  
}  
return head;  
}  
  
ArrayCyclicLinkListDeserialize(arr) {  
if (arr.length === 0) { return null; }  
let head = new Node(arr[0]);  
let current = head;  
for (let i = 1; i < arr.length; i++) {  
[current.next](http://current.next/) = new Node(arr[i]);  
current = current.next;  
// see if works with lc Question  
[if(current.next](http://if%28current.next/) === null){  
[current.next](http://current.next/) = head;  
}  
}  
return head;  
}  
  
  
// fix  
ArrayLinkListDoubleDeserialize(arr) {  
if (arr.length === 0) { return null; }  
let head = new DoubleLLNode(arr[0]);  
let current = head;  
// tail  
  
for (let i = 1; i < arr.length; i++) {  
[current.next](http://current.next/) = new ListNode(arr[i]);  
current = current.next;  
}  
// this.tail = head;  
return head;  
}  
  
ArrayTreeDeserialize(arr) {  
if (arr.length === 0) { return null; }  
let root = new TreeNode(arr[0]);  
let queue = [root];  
for(let i = 1; i < arr.length; i += 2) {  
let current = queue.shift();  
if (arr[i] !== null) {  
current.left = new TreeNode(arr[i]);  
queue.push(current.left);  
}  
if (arr[i + 1] !== null && arr[i + 1] !== undefined) {  
current.right = new TreeNode(arr[i + 1]);  
queue.push(current.right);  
}  
}  
return root;  
}  
  
  
ArrayGraphDeserialize(nodeIdx, edges) {  
let vertices = {};  
while (nodeIdx--) {  
vertices[nodeIdx] = new Vertex(nodeIdx);  
  
}  
let v1;  
let v2;  
  
edges.forEach((edge) => {  
  
v1 = edge[0];  
v2 = edge[1];  
  
vertices[v1].edges.push(vertices[v2]);  
vertices[v2].edges.push(vertices[v1]);  
  
}  
  
);  
  
return vertices[0];  
}  
  
}  
  
let LinkListArray = [1,5,7,10];  
let TreeArray = [4, 2, 5, 1, 3, null, 7, null, null, null, null, 6, 8]  
  
  
let idGraphIndex = 8;  
let GraphRelationshipArray = [  
[0, 1],  
[1, 2],  
[2, 4],  
[3, 5],  
[4, 5],  
[1, 7],  
[4, 6],  
[4, 7],  
[5, 6],  
];  
  
const stuructureMaker = new NodeConstructor();  
  
// let linkedList = console.log(stuructureMaker.ArrayLinkListDeserialize(LinkListArray))  
// let linkedListDD = console.log(stuructureMaker.ArrayLinkListDoubleDeserialize(LinkListArray))  
let tree = console.log(stuructureMaker.ArrayTreeDeserialize((TreeArray)));  
// let graph = console.log(stuructureMaker.ArrayGraphDeserialize(idGraphIndex, GraphRelationshipArray))  
  
module.exports = NodeConstructor;  
  
// use were you implement  
const linkSetter = require("../../../_DataStructuresBuiltUpClasses/DataStrucFactoryInterview");  
const linkedGetter = new linkSetter();