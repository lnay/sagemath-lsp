# Outline of strategy for the experiments in this repo

- [ ] MVP with functioning (approximate is ok) go-to-definition using `sage --preparse` and some existing Python language server
  - find limitations (how unpredictable are the lines and rows of corresponding items between SageMath and Python)
  - experiment with different Python language servers
- [ ] Replace usage of `sage --preparse` with the tree-sitter parser bindings using [TS grammar](https://github.com/havarddj/tree-sitter-sage/tree/main)
  - consider appropriate structure to keep track of the mapping between SageMath and Python:
    - how much code is actually modified in practice?
    - if expansions can be kept within a line => concise encoding of mapping on specific lines where necessary?
    - bookkeeping of mapping across the whole abstract syntax tree?
- [ ] Implement other LSP capabilities
  - [ ] hover
  - [ ] completion
  - [ ] signature help
  - [ ] diagnostics
    - find any diagnostics which no longer make sense in the original SageMath code
  - [ ] formatting
  - [ ] rename
  - [ ] code actions?? maybe this cannot be delegated to Python language server
