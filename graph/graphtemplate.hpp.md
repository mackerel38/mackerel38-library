---
data:
  _extendedDependsOn: []
  _extendedRequiredBy: []
  _extendedVerifiedWith: []
  _isVerificationFailed: false
  _pathExtension: hpp
  _verificationStatusIcon: ':warning:'
  attributes:
    links: []
  bundledCode: "#line 2 \"graph/graphtemplate.hpp\"\n#include<bits/stdc++.h>\nusing\
    \ namespace std;\ntemplate <typename T = int>\nstruct edge {\n  int from, to;\n\
    \  T cost;\n  int id;\n  edge(int _from, int _to, T _cost = 1, int _id = -1) :\
    \ from(_from), to(_to), cost(_cost), id(_id) {}\n  // operator int() const { return\
    \ to; }\n};\n\ntemplate <typename T = int>\nstruct graph {\n  vector<vector<edge<T>>>\
    \ data;\n  int edges;\n  graph(int n) : data(n), es(0) {}\n  void add_directed_edge(int\
    \ from, int to, T cost = 1) {\n    data[from].push_back(from, to, cost, edges++);\n\
    \  }\n  void add_edge(int from, int to, T cost = 1) {\n    g[from].emplace_back(from,\
    \ to, cost, es);\n    g[to].emplace_back(to, from, cost, es++);\n  }\n  void read(int\
    \ M, int padding = -1, bool weighted = false,\n            bool directed = false)\
    \ {\n    for (int i = 0; i < M; i++) {\n      int a, b;\n      cin >> a >> b;\n\
    \      a += padding;\n      b += padding;\n      T c = T(1);\n      if (weighted)\
    \ cin >> c;\n      if (directed)\n        add_directed_edge(a, b, c);\n      else\n\
    \        add_edge(a, b, c);\n    }\n  }\n\n  inline vector<Edge<T> > &operator[](const\
    \ int &k) { return g[k]; }\n\n  inline const vector<Edge<T> > &operator[](const\
    \ int &k) const { return g[k]; }\n};\n\ntemplate <typename T = int>\nusing Edges\
    \ = vector<Edge<T> >;\n"
  code: "#pragma once\n#include<bits/stdc++.h>\nusing namespace std;\ntemplate <typename\
    \ T = int>\nstruct edge {\n  int from, to;\n  T cost;\n  int id;\n  edge(int _from,\
    \ int _to, T _cost = 1, int _id = -1) : from(_from), to(_to), cost(_cost), id(_id)\
    \ {}\n  // operator int() const { return to; }\n};\n\ntemplate <typename T = int>\n\
    struct graph {\n  vector<vector<edge<T>>> data;\n  int edges;\n  graph(int n)\
    \ : data(n), es(0) {}\n  void add_directed_edge(int from, int to, T cost = 1)\
    \ {\n    data[from].push_back(from, to, cost, edges++);\n  }\n  void add_edge(int\
    \ from, int to, T cost = 1) {\n    g[from].emplace_back(from, to, cost, es);\n\
    \    g[to].emplace_back(to, from, cost, es++);\n  }\n  void read(int M, int padding\
    \ = -1, bool weighted = false,\n            bool directed = false) {\n    for\
    \ (int i = 0; i < M; i++) {\n      int a, b;\n      cin >> a >> b;\n      a +=\
    \ padding;\n      b += padding;\n      T c = T(1);\n      if (weighted) cin >>\
    \ c;\n      if (directed)\n        add_directed_edge(a, b, c);\n      else\n \
    \       add_edge(a, b, c);\n    }\n  }\n\n  inline vector<Edge<T> > &operator[](const\
    \ int &k) { return g[k]; }\n\n  inline const vector<Edge<T> > &operator[](const\
    \ int &k) const { return g[k]; }\n};\n\ntemplate <typename T = int>\nusing Edges\
    \ = vector<Edge<T> >;\n"
  dependsOn: []
  isVerificationFile: false
  path: graph/graphtemplate.hpp
  requiredBy: []
  timestamp: '2025-04-01 16:03:04+09:00'
  verificationStatus: LIBRARY_NO_TESTS
  verifiedWith: []
documentation_of: graph/graphtemplate.hpp
layout: document
redirect_from:
- /library/graph/graphtemplate.hpp
- /library/graph/graphtemplate.hpp.html
title: graph/graphtemplate.hpp
---
