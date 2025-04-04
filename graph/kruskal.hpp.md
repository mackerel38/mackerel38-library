---
data:
  _extendedDependsOn:
  - icon: ':heavy_check_mark:'
    path: graph/graphtemplate.hpp
    title: graph/graphtemplate.hpp
  - icon: ':heavy_check_mark:'
    path: structure/UnionFind.hpp
    title: structure/UnionFind.hpp
  _extendedRequiredBy: []
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
    \       return data[k];\n    }\n};\n#line 3 \"structure/UnionFind.hpp\"\nusing\
    \ namespace std;\nstruct UnionFind {\n    int _n;\n    vector<int> data;\n   \
    \ // _n \u500B\u306E\u8981\u7D20\u304B\u3089\u306A\u308BUnionFind \u3092\u69CB\
    \u7BC9 O(n)\n    UnionFind(int n) : _n(n), data(n, -1) {}\n    // 2 \u3064\u306E\
    \u8981\u7D20\u3092\u4F75\u5408 O(\u03B1(n))\n    bool merge(int p, int q) {\n\
    \        p = root(p);\n        q = root(q);\n        if (p == q) return false;\n\
    \        if (q < p) swap(p, q);\n        data[p] += data[q];\n        data[q]\
    \ = p;\n        return true;\n    }\n    // \u89AA\u8981\u7D20\u3092\u53D6\u5F97\
    \ O(\u03B1(n))\n    int root(int p) {\n        assert(0 <= p && p < _n);\n   \
    \     if (data[p] < 0) {\n            return p;\n        } else {\n          \
    \  data[p] = root(data[p]);\n            return data[p];\n        }\n    }\n \
    \   // \u89AA\u8981\u7D20\u3092\u53D6\u5F97 O(\u03B1(n))\n    int operator[](int\
    \ p) {\n        return root(p);\n    }\n    // 2 \u3064\u306E\u8981\u7D20\u304C\
    \u540C\u3058\u96C6\u5408\u306B\u542B\u307E\u308C\u308B\u304B\u5224\u5B9A O(\u03B1\
    (n))\n    bool same(int p, int q) {\n        return root(p) == root(q);\n    }\n\
    \    // \u8981\u7D20\u304C\u5C5E\u3059\u308B\u96C6\u5408\u306E\u5927\u304D\u3055\
    \u3092\u8FD4\u3059 O(\u03B1(n))\n    int size(int p) {\n        return -data[root(p)];\n\
    \    }\n    // UnionFind \u306E\u9023\u7D50\u6210\u5206\u306Evector \u3092\u8FD4\
    \u3059 O(n \u03B1(n))\n    vector<vector<int>> groups() {\n        vector<vector<int>>\
    \ re(_n);\n        for (int i=0; i<_n; i++) re[root(i)].push_back(i);\n      \
    \  re.erase(remove_if(re.begin(), re.end(), [](vector<int>& v){ return v.empty();\
    \ }), re.end());\n        return re;\n    }\n};\n#line 5 \"graph/kruskal.hpp\"\
    \nusing namespace std;\ntemplate<class T=int>\ngraph<T> kruskal(graph<T>& g) {\n\
    \    edges<T> _edges = g.getedges();\n    graph<T> re(g.size(), false, true);\n\
    \    sort(_edges.begin(), _edges.end(), [](edge<T>& a, edge<T>& b) { return a.cost\
    \ < b.cost; });\n    UnionFind uf(g.size());\n    for (auto& _e : _edges) {\n\
    \        if (uf.merge(_e.from, _e.to)) {\n            re.add_edge(_e);\n     \
    \   }\n    }\n    return re;\n}\n"
  code: "#pragma once\n#include \"graphtemplate\"\n#include \"UnionFind\"\n#include<bits/stdc++.h>\n\
    using namespace std;\ntemplate<class T=int>\ngraph<T> kruskal(graph<T>& g) {\n\
    \    edges<T> _edges = g.getedges();\n    graph<T> re(g.size(), false, true);\n\
    \    sort(_edges.begin(), _edges.end(), [](edge<T>& a, edge<T>& b) { return a.cost\
    \ < b.cost; });\n    UnionFind uf(g.size());\n    for (auto& _e : _edges) {\n\
    \        if (uf.merge(_e.from, _e.to)) {\n            re.add_edge(_e);\n     \
    \   }\n    }\n    return re;\n}"
  dependsOn:
  - graph/graphtemplate.hpp
  - structure/UnionFind.hpp
  isVerificationFile: false
  path: graph/kruskal.hpp
  requiredBy: []
  timestamp: '2025-04-02 02:12:40+09:00'
  verificationStatus: LIBRARY_ALL_AC
  verifiedWith:
  - verify/yosupo-minimum_spanning_tree.test.cpp
documentation_of: graph/kruskal.hpp
layout: document
redirect_from:
- /library/graph/kruskal.hpp
- /library/graph/kruskal.hpp.html
title: graph/kruskal.hpp
---
