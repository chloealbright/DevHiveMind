try

function createGraph(vertices, edges) {  
const graph = {};  
for (const vertex of vertices) {  
graph[vertex.id] = { id: vertex.id, edges: [] };  
}  
for (const edge of edges) {  
if (!graph[edge.source].edges.includes(edge.target)) {  
graph[edge.source].edges.push(edge.target);  
}  
if (!graph[edge.target].edges.includes(edge.source)) {  
graph[edge.target].edges.push(edge.source);  
}  
}  
return Object.values(graph);  
}



Old 

function ArrayGraphDeserialize(nodeIdx, edges) {  
let vertices = {};  
  
for (let i = 1; i <= nodeIdx; i++) {  
vertices[i] = new Vertex(i);  
}  
  
let v1, v2;  
  
edges.forEach((edge) => {  
v1 = edge[0];  
v2 = edge[1];  
  
vertices[v1].edges.push(vertices[v2]);  
vertices[v2].edges.push(vertices[v1]);  
});  
  
return vertices;  
}