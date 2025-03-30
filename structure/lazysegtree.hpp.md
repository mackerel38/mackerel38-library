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
  bundledCode: "#line 2 \"structure/lazysegtree.hpp\"\n#include<bits/stdc++.h>\nusing\
    \ namespace std;\ntemplate<class S, auto op, auto F, auto mapping, auto composition>\n\
    struct lazysegtree {\n    int n, size, sz;\n    S e;\n    F id;\n    vector<S>\
    \ data;\n    vector<S> lazy;\n    // \u9045\u5EF6\u4F1D\u64AD\u30BB\u30B0\u30E1\
    \u30F3\u30C8\u6728\u3092\u69CB\u7BC9 O(n)\n    lazysegtree(int n, S e(), F id())\
    \ : n(n), e(e), id(id) {\n        sz = 0;\n        while ((1 << sz) < n) sz++;\n\
    \        size = 1 << sz;\n        data.assign(2 * size, e);\n        lazy.assign(size,\
    \ id);\n    }\n    // \u9045\u5EF6\u4F1D\u64AD\u30BB\u30B0\u30E1\u30F3\u30C8\u6728\
    \u3092\u69CB\u7BC9 O(n)\n    lazysegtree(vector<S>& v, S e(), F id()) : lazysegtree(v.size(),\
    \ e, id) {\n        for (int i=0; i<n; i++) data[size + i] = v[i];\n        for\
    \ (int k=size-1; 0<k; k--) update(k);\n    }\n    void update(int k) {\n     \
    \   data[k] = op(data[2*k], data[2*k+1]);\n        if (lazy[k] != id) {\n    \
    \        data[k] = mapping(lazy[k], data[k]);\n            if (k < size) {\n \
    \               lazy[2*k] = composition(lazy[k], lazy[2*k]);\n               \
    \ lazy[2*k+1] = composition(lazy[k], lazy[2*k+1]);\n            }\n          \
    \  lazy[k] = id;\n        }\n    }\n    // \u9045\u5EF6\u4F1D\u64AD\u3092\u9069\
    \u7528\u3059\u308B O(log n)\n    void apply(int k, F x) {\n        assert(0 <=\
    \ k && k < size);\n        data[k] = mapping(x, data[k]);\n        if (k < size)\
    \ {\n            lazy[k] = composition(x, lazy[k]);\n        }\n    }\n    //\
    \ \u5024\u306E\u5909\u66F4 O(log n)\n    void set(int p, S x) {\n        assert(0\
    \ <= p && p < n);\n        p += size;\n        data[p] = x;\n        for (int\
    \ k=p>>1; 0<k; k>>=1) {\n            update(k);\n        }\n    }\n    // p\u756A\
    \u76EE\u306E\u5024\u3092\u53D6\u5F97\u3059\u308B O(log n)\n    S get(int p) {\n\
    \        assert(0 <= p && p < n);\n        p += size;\n        for (int k=sz;\
    \ 0<k; k--) {\n            update(p >> k);\n        }\n        return data[p];\n\
    \    }\n    // p\u756A\u76EE\u306E\u5024\u3092\u53D6\u5F97\u3059\u308B O(log n)\n\
    \    S operator[](int p) {\n        return get(p);\n    }\n    // \u533A\u9593\
    [l, r)\u306E\u5024\u3092\u53D6\u5F97 O(log n)\n    S prod(int l, int r) {\n  \
    \      assert(0 <= l && l <= r && r <= n);\n        if (l == r) return e;\n  \
    \      l += size;\n        r += size;\n        for (int k=sz; 0<k; k--) {\n  \
    \          if (((l >> k) << k) != l) update(l >> k);\n            if (((r >> k)\
    \ << k) != r) update(r >> k);\n        }\n        S resl = e, resr = e;\n    \
    \    while (l < r) {\n            if (l & 1) resl = op(resl, data[l++]);\n   \
    \         if (r & 1) resr = op(data[--r], resr);\n            l >>= 1;\n     \
    \       r >>= 1;\n        }\n        return op(resl, resr);\n    }\n    // \u533A\
    \u9593[l, r)\u306B\u9045\u5EF6\u4F1D\u64AD\u3092\u9069\u7528\u3059\u308B O(log\
    \ n)\n    void apply(int l, int r, S x) {\n        assert(0 <= l && l <= r &&\
    \ r <= n);\n        if (l == r) return;\n        l += size;\n        r += size;\n\
    \        for (int k=sz; 0<k; k--) {\n            if (((l >> k) << k) != l) update(l\
    \ >> k);\n            if (((r >> k) << k) != r) update(r >> k);\n        }\n \
    \       while (l < r) {\n            if (l & 1) apply(l++, x);\n            if\
    \ (r & 1) apply(--r, x);\n            l >>= 1;\n            r >>= 1;\n       \
    \ }\n    }\n    // \u533A\u9593[0, n) \u306E\u5024\u3092\u53D6\u5F97 O(1)\n  \
    \  S all_prod() {\n        return data[1];\n    }\n    // f(op([l, r)))=true \u3068\
    \u306A\u308B\u6700\u5927\u306Er \u3092\u8FD4\u3059 O(log n)\n    template<auto\
    \ f>\n    int max_right(int l) {\n        assert(f(e));\n        assert(0 <= l\
    \ && l <= n);\n        if (l == n) return l;\n        l += size;\n        S s\
    \ = e;\n        do {\n            while (l % 2 == 0) l >>= 1;\n            if\
    \ (!f(op(s, data[l]))) {\n                while (l < size) {\n               \
    \     l = 2 * l;\n                    if (f(op(s, data[l]))) s = op(s, data[l++]);\n\
    \                }\n                return l - size;\n            }\n        \
    \    s = op(s, data[l++]);\n        } while ((l & -l) != l);\n        return n;\n\
    \    }\n    // f(op([l, r)))=true \u3068\u306A\u308B\u6700\u5C0F\u306El \u3092\
    \u8FD4\u3059 O(log n)\n    template<auto f>\n    int min_left(int r) {\n     \
    \   assert(f(e));\n        assert(0 <= r && r <= n);\n        if (r == 0) return\
    \ r;\n        r += size;\n        S s = e;\n        do {\n            r--;\n \
    \           while (r > 1 && r % 2 == 1) r >>= 1;\n            if (!f(op(data[r],\
    \ s))) {\n                while (r < size) {\n                    if (f(op(data[2*r],\
    \ s))) s = op(data[2*r], s);\n                    r = 2 * r + 1;\n           \
    \     }\n                return r - size + 1;\n            }\n            s =\
    \ op(data[r--], s);\n        } while ((r & -r) != r);\n        return 0;\n   \
    \ }\n};\n"
  code: "#pragma once\n#include<bits/stdc++.h>\nusing namespace std;\ntemplate<class\
    \ S, auto op, auto F, auto mapping, auto composition>\nstruct lazysegtree {\n\
    \    int n, size, sz;\n    S e;\n    F id;\n    vector<S> data;\n    vector<S>\
    \ lazy;\n    // \u9045\u5EF6\u4F1D\u64AD\u30BB\u30B0\u30E1\u30F3\u30C8\u6728\u3092\
    \u69CB\u7BC9 O(n)\n    lazysegtree(int n, S e(), F id()) : n(n), e(e), id(id)\
    \ {\n        sz = 0;\n        while ((1 << sz) < n) sz++;\n        size = 1 <<\
    \ sz;\n        data.assign(2 * size, e);\n        lazy.assign(size, id);\n   \
    \ }\n    // \u9045\u5EF6\u4F1D\u64AD\u30BB\u30B0\u30E1\u30F3\u30C8\u6728\u3092\
    \u69CB\u7BC9 O(n)\n    lazysegtree(vector<S>& v, S e(), F id()) : lazysegtree(v.size(),\
    \ e, id) {\n        for (int i=0; i<n; i++) data[size + i] = v[i];\n        for\
    \ (int k=size-1; 0<k; k--) update(k);\n    }\n    void update(int k) {\n     \
    \   data[k] = op(data[2*k], data[2*k+1]);\n        if (lazy[k] != id) {\n    \
    \        data[k] = mapping(lazy[k], data[k]);\n            if (k < size) {\n \
    \               lazy[2*k] = composition(lazy[k], lazy[2*k]);\n               \
    \ lazy[2*k+1] = composition(lazy[k], lazy[2*k+1]);\n            }\n          \
    \  lazy[k] = id;\n        }\n    }\n    // \u9045\u5EF6\u4F1D\u64AD\u3092\u9069\
    \u7528\u3059\u308B O(log n)\n    void apply(int k, F x) {\n        assert(0 <=\
    \ k && k < size);\n        data[k] = mapping(x, data[k]);\n        if (k < size)\
    \ {\n            lazy[k] = composition(x, lazy[k]);\n        }\n    }\n    //\
    \ \u5024\u306E\u5909\u66F4 O(log n)\n    void set(int p, S x) {\n        assert(0\
    \ <= p && p < n);\n        p += size;\n        data[p] = x;\n        for (int\
    \ k=p>>1; 0<k; k>>=1) {\n            update(k);\n        }\n    }\n    // p\u756A\
    \u76EE\u306E\u5024\u3092\u53D6\u5F97\u3059\u308B O(log n)\n    S get(int p) {\n\
    \        assert(0 <= p && p < n);\n        p += size;\n        for (int k=sz;\
    \ 0<k; k--) {\n            update(p >> k);\n        }\n        return data[p];\n\
    \    }\n    // p\u756A\u76EE\u306E\u5024\u3092\u53D6\u5F97\u3059\u308B O(log n)\n\
    \    S operator[](int p) {\n        return get(p);\n    }\n    // \u533A\u9593\
    [l, r)\u306E\u5024\u3092\u53D6\u5F97 O(log n)\n    S prod(int l, int r) {\n  \
    \      assert(0 <= l && l <= r && r <= n);\n        if (l == r) return e;\n  \
    \      l += size;\n        r += size;\n        for (int k=sz; 0<k; k--) {\n  \
    \          if (((l >> k) << k) != l) update(l >> k);\n            if (((r >> k)\
    \ << k) != r) update(r >> k);\n        }\n        S resl = e, resr = e;\n    \
    \    while (l < r) {\n            if (l & 1) resl = op(resl, data[l++]);\n   \
    \         if (r & 1) resr = op(data[--r], resr);\n            l >>= 1;\n     \
    \       r >>= 1;\n        }\n        return op(resl, resr);\n    }\n    // \u533A\
    \u9593[l, r)\u306B\u9045\u5EF6\u4F1D\u64AD\u3092\u9069\u7528\u3059\u308B O(log\
    \ n)\n    void apply(int l, int r, S x) {\n        assert(0 <= l && l <= r &&\
    \ r <= n);\n        if (l == r) return;\n        l += size;\n        r += size;\n\
    \        for (int k=sz; 0<k; k--) {\n            if (((l >> k) << k) != l) update(l\
    \ >> k);\n            if (((r >> k) << k) != r) update(r >> k);\n        }\n \
    \       while (l < r) {\n            if (l & 1) apply(l++, x);\n            if\
    \ (r & 1) apply(--r, x);\n            l >>= 1;\n            r >>= 1;\n       \
    \ }\n    }\n    // \u533A\u9593[0, n) \u306E\u5024\u3092\u53D6\u5F97 O(1)\n  \
    \  S all_prod() {\n        return data[1];\n    }\n    // f(op([l, r)))=true \u3068\
    \u306A\u308B\u6700\u5927\u306Er \u3092\u8FD4\u3059 O(log n)\n    template<auto\
    \ f>\n    int max_right(int l) {\n        assert(f(e));\n        assert(0 <= l\
    \ && l <= n);\n        if (l == n) return l;\n        l += size;\n        S s\
    \ = e;\n        do {\n            while (l % 2 == 0) l >>= 1;\n            if\
    \ (!f(op(s, data[l]))) {\n                while (l < size) {\n               \
    \     l = 2 * l;\n                    if (f(op(s, data[l]))) s = op(s, data[l++]);\n\
    \                }\n                return l - size;\n            }\n        \
    \    s = op(s, data[l++]);\n        } while ((l & -l) != l);\n        return n;\n\
    \    }\n    // f(op([l, r)))=true \u3068\u306A\u308B\u6700\u5C0F\u306El \u3092\
    \u8FD4\u3059 O(log n)\n    template<auto f>\n    int min_left(int r) {\n     \
    \   assert(f(e));\n        assert(0 <= r && r <= n);\n        if (r == 0) return\
    \ r;\n        r += size;\n        S s = e;\n        do {\n            r--;\n \
    \           while (r > 1 && r % 2 == 1) r >>= 1;\n            if (!f(op(data[r],\
    \ s))) {\n                while (r < size) {\n                    if (f(op(data[2*r],\
    \ s))) s = op(data[2*r], s);\n                    r = 2 * r + 1;\n           \
    \     }\n                return r - size + 1;\n            }\n            s =\
    \ op(data[r--], s);\n        } while ((r & -r) != r);\n        return 0;\n   \
    \ }\n};"
  dependsOn: []
  isVerificationFile: false
  path: structure/lazysegtree.hpp
  requiredBy: []
  timestamp: '2025-03-31 06:02:04+09:00'
  verificationStatus: LIBRARY_NO_TESTS
  verifiedWith: []
documentation_of: structure/lazysegtree.hpp
layout: document
redirect_from:
- /library/structure/lazysegtree.hpp
- /library/structure/lazysegtree.hpp.html
title: structure/lazysegtree.hpp
---
