---
data:
  _extendedDependsOn: []
  _extendedRequiredBy:
  - icon: ':heavy_check_mark:'
    path: graph/kruskal.hpp
    title: graph/kruskal.hpp
  _extendedVerifiedWith:
  - icon: ':heavy_check_mark:'
    path: verify/yosupo-minimum_spanning_tree.test.cpp
    title: verify/yosupo-minimum_spanning_tree.test.cpp
  _isVerificationFailed: false
  _pathExtension: hpp
  _verificationStatusIcon: ':heavy_check_mark:'
  attributes:
    links: []
  bundledCode: "#line 2 \"graph/graphtemplate.hpp\"\n#include<bits/stdc++.h>\nusing\
    \ namespace std;\ntemplate<class T = int>\nstruct edge {\n    int from, to;\n\
    \    T cost;\n    int id;\n    edge(int _from, int _to, T _cost = 1, int _id =\
    \ -1) : from(_from), to(_to), cost(_cost), id(_id) {}\n};\ntemplate<class T>\n\
    using edges = vector<edge<T>>;\ntemplate<class T = int>\nstruct graph {\n    vector<vector<edge<T>>>\
    \ data;\n    vector<edge<T>> _edges;\n    bool _directed, _weighted;\n    T sumcost;\n\
    \    graph(int n, bool directed=false, bool weighted=false) : data(n), _directed(directed),\
    \ _weighted(weighted), sumcost(T{}) {}\n    void add_edge(int from, int to, T\
    \ cost = 1, int id=-1) {\n        if (id == -1) id = _edges.size();\n        data[from].push_back(edge(from,\
    \ to, cost, id));\n        _edges.push_back(edge(from, to, cost, id));\n     \
    \   id++;\n        sumcost += cost;\n        if (_directed) {\n            data[to].push_back(edge(to,\
    \ from, cost, id));\n            _edges.push_back(edge(to, from, cost, id));\n\
    \            id++;\n            sumcost += cost;\n        }\n    }\n    void add_edge(edge<T>&\
    \ _e) {\n        add_edge(_e.from, _e.to, _e.cost, _e.id);\n    }\n    void read(int\
    \ m, int indexed = 1) {\n        for (int i=0; i<m; i++) {\n            int from,\
    \ to, cost=1;\n            cin >> from >> to;\n            if (_weighted) cin\
    \ >> cost;\n            add_edge(from - indexed, to - indexed, cost);\n      \
    \  }\n    }\n    int size() {\n        return data.size();\n    }\n    edges<T>\
    \ getedges() {\n        return _edges;\n    }\n    edge<T> getedge(int p) {\n\
    \        return _edges[p];\n    }\n    vector<edge<T>> operator[](int k) {\n \
    \       return data[k];\n    }\n};\n"
  code: "#pragma once\n#include<bits/stdc++.h>\nusing namespace std;\ntemplate<class\
    \ T = int>\nstruct edge {\n    int from, to;\n    T cost;\n    int id;\n    edge(int\
    \ _from, int _to, T _cost = 1, int _id = -1) : from(_from), to(_to), cost(_cost),\
    \ id(_id) {}\n};\ntemplate<class T>\nusing edges = vector<edge<T>>;\ntemplate<class\
    \ T = int>\nstruct graph {\n    vector<vector<edge<T>>> data;\n    vector<edge<T>>\
    \ _edges;\n    bool _directed, _weighted;\n    T sumcost;\n    graph(int n, bool\
    \ directed=false, bool weighted=false) : data(n), _directed(directed), _weighted(weighted),\
    \ sumcost(T{}) {}\n    void add_edge(int from, int to, T cost = 1, int id=-1)\
    \ {\n        if (id == -1) id = _edges.size();\n        data[from].push_back(edge(from,\
    \ to, cost, id));\n        _edges.push_back(edge(from, to, cost, id));\n     \
    \   id++;\n        sumcost += cost;\n        if (_directed) {\n            data[to].push_back(edge(to,\
    \ from, cost, id));\n            _edges.push_back(edge(to, from, cost, id));\n\
    \            id++;\n            sumcost += cost;\n        }\n    }\n    void add_edge(edge<T>&\
    \ _e) {\n        add_edge(_e.from, _e.to, _e.cost, _e.id);\n    }\n    void read(int\
    \ m, int indexed = 1) {\n        for (int i=0; i<m; i++) {\n            int from,\
    \ to, cost=1;\n            cin >> from >> to;\n            if (_weighted) cin\
    \ >> cost;\n            add_edge(from - indexed, to - indexed, cost);\n      \
    \  }\n    }\n    int size() {\n        return data.size();\n    }\n    edges<T>\
    \ getedges() {\n        return _edges;\n    }\n    edge<T> getedge(int p) {\n\
    \        return _edges[p];\n    }\n    vector<edge<T>> operator[](int k) {\n \
    \       return data[k];\n    }\n};\n"
  dependsOn: []
  isVerificationFile: false
  path: graph/graphtemplate.hpp
  requiredBy:
  - graph/kruskal.hpp
  timestamp: '2025-04-02 02:12:40+09:00'
  verificationStatus: LIBRARY_ALL_AC
  verifiedWith:
  - verify/yosupo-minimum_spanning_tree.test.cpp
documentation_of: graph/graphtemplate.hpp
layout: document
redirect_from:
- /library/graph/graphtemplate.hpp
- /library/graph/graphtemplate.hpp.html
title: graph/graphtemplate.hpp
---
