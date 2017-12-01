# JS Node.*

## Node.contains()

* `node.contains(anotherNode);`

> The Node.contains() method returns a Boolean value indicating whether a node is a descendant of a given node or not.

## Selection.containsNode()

### selection

> A Selection object represents the range of text selected by the user or the current position of the caret. 
> To obtain a Selection object for examination or modification, call `window.getSelection()`.

 * selection 代表 当前用户选中的内容 或者 当前插入符的位置
 * 使用 `window.getSelection()`获取

### Selection.coantainsNode()

`sel.containsNode(node,true/false)`
在 selection 中检测是否包含`node`这个节点;
当第二个参数设置为`true`则: 即使`node`只有部分在 selection 中也会返回 `true`;
若设为`false`,则只有在完全包含`node`时才返回`true`
 