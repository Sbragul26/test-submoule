### Testing of the Create Nodes to Represent Tree Structure Feature

The functionality to create nodes representing a tree structure was tested. The following issue was observed:

- When tree sub-nodes (e.g., **Tree1**, **Tree2**) are created, they are labeled sequentially.
- However, after deleting these nodes, the label counter does not reset. The next created node is labeled as **Tree3**, instead of restarting from **Tree1**.

This behavior may lead to confusion, as the numbering does not ref
