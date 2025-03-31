---
data:
  _extendedDependsOn: []
  _extendedRequiredBy: []
  _extendedVerifiedWith:
  - icon: ':heavy_check_mark:'
    path: verify/yosupo-primality_test.test.cpp
    title: verify/yosupo-primality_test.test.cpp
  _isVerificationFailed: false
  _pathExtension: hpp
  _verificationStatusIcon: ':heavy_check_mark:'
  attributes:
    links: []
  bundledCode: "#line 2 \"math/prime.hpp\"\n#include <bits/stdc++.h>\nusing namespace\
    \ std;\n// \u7D20\u6570\u5224\u5B9A O(log n)\nbool isprime(long long n) {\n  \
    \  if (n <= 1) return false;\n    if (n == 2) return true;\n    if (n % 2 == 0)\
    \ return false;\n    int flag = 1;\n    if (n < 4759123141LL) flag = 0;\n    vector<vector<long\
    \ long>> tests = {{2, 7, 61}, {2, 325, 9375, 28178, 450775, 9780504, 1795265022}};\n\
    \    long long s = 0, d = n - 1;\n    while (d % 2 == 0) {\n        ++s;\n   \
    \     d >>= 1;\n    }\n    for (auto a : tests[flag]) {\n        if (n <= a) return\
    \ true;\n        __int128_t x = 1, a2=a%n, d2 = d;\n        while (d2) {\n   \
    \         if (d2 & 1) x = x * a2 % n;\n            a2 = a2 * a2 % n;\n       \
    \     d2 >>= 1;\n        }\n        if (x != 1) {\n            long long t;\n\
    \            for (t = 0; t < s; ++t) {\n                if (x == n - 1) break;\n\
    \                x = x * x % n;\n            }\n            if (t == s) return\
    \ false;\n        }\n    }\n    return true;\n}\n"
  code: "#pragma once\n#include <bits/stdc++.h>\nusing namespace std;\n// \u7D20\u6570\
    \u5224\u5B9A O(log n)\nbool isprime(long long n) {\n    if (n <= 1) return false;\n\
    \    if (n == 2) return true;\n    if (n % 2 == 0) return false;\n    int flag\
    \ = 1;\n    if (n < 4759123141LL) flag = 0;\n    vector<vector<long long>> tests\
    \ = {{2, 7, 61}, {2, 325, 9375, 28178, 450775, 9780504, 1795265022}};\n    long\
    \ long s = 0, d = n - 1;\n    while (d % 2 == 0) {\n        ++s;\n        d >>=\
    \ 1;\n    }\n    for (auto a : tests[flag]) {\n        if (n <= a) return true;\n\
    \        __int128_t x = 1, a2=a%n, d2 = d;\n        while (d2) {\n           \
    \ if (d2 & 1) x = x * a2 % n;\n            a2 = a2 * a2 % n;\n            d2 >>=\
    \ 1;\n        }\n        if (x != 1) {\n            long long t;\n           \
    \ for (t = 0; t < s; ++t) {\n                if (x == n - 1) break;\n        \
    \        x = x * x % n;\n            }\n            if (t == s) return false;\n\
    \        }\n    }\n    return true;\n}"
  dependsOn: []
  isVerificationFile: false
  path: math/prime.hpp
  requiredBy: []
  timestamp: '2025-03-31 23:40:20+09:00'
  verificationStatus: LIBRARY_ALL_AC
  verifiedWith:
  - verify/yosupo-primality_test.test.cpp
documentation_of: math/prime.hpp
layout: document
redirect_from:
- /library/math/prime.hpp
- /library/math/prime.hpp.html
title: math/prime.hpp
---
