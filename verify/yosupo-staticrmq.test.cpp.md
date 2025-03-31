---
data:
  _extendedDependsOn:
  - icon: ':heavy_check_mark:'
    path: structure/sparsetable.hpp
    title: structure/sparsetable.hpp
  _extendedRequiredBy: []
  _extendedVerifiedWith: []
  _isVerificationFailed: false
  _pathExtension: cpp
  _verificationStatusIcon: ':heavy_check_mark:'
  attributes:
    '*NOT_SPECIAL_COMMENTS*': ''
    PROBLEM: https://judge.yosupo.jp/problem/staticrmq
    links:
    - https://judge.yosupo.jp/problem/staticrmq
  bundledCode: "#line 1 \"verify/yosupo-staticrmq.test.cpp\"\n#define PROBLEM \"https://judge.yosupo.jp/problem/staticrmq\"\
    \r\n#ifdef poe\r\n#define debug(x) cerr<<#x<<\": \"<<x<<endl\r\n#else\r\n#define\
    \ debug(x)\r\n// #pragma GCC target(\"arch=skylake-avx512\")\r\n// #pragma GCC\
    \ target(\"avx2\")\r\n// #pragma GCC optimize(\"O3\")\r\n// #pragma GCC optimize(\"\
    unroll-loops\")\r\n#endif\r\n#include<bits/stdc++.h>\r\nusing namespace std;\r\
    \nusing ll=long long;\r\nusing ull=unsigned long long;\r\nusing ld=long double;\r\
    \nusing pi=pair<int,int>;\r\nusing pll=pair<ll,ll>;\r\nusing str=string;\r\ntemplate<class\
    \ T>using vec=vector<T>;\r\nusing vi=vec<int>;using vvi=vec<vi>;using vvvi=vec<vvi>;using\
    \ vvvvi=vec<vvvi>;using vvvvvi=vec<vvvvi>;\r\nusing vll=vec<ll>;using vvll=vec<vll>;using\
    \ vvvll=vec<vvll>;using vvvvll=vec<vvvll>;using vvvvvll=vec<vvvvll>;\r\nusing\
    \ vpi=vec<pi>;using vvpi=vec<vpi>;using vvvpi=vec<vvpi>;using vvvvpi=vec<vvvpi>;using\
    \ vvvvvpi=vec<vvvvpi>;\r\nusing vpll=vec<pll>;using vvpll=vec<vpll>;using vvvpll=vec<vvpll>;using\
    \ vvvvpll=vec<vvvpll>;using vvvvvpll=vec<vvvvpll>;\r\ntemplate<class T>using pq=priority_queue<T,vector<T>>;\r\
    \ntemplate<class T>using pqg=priority_queue<T,vector<T>,greater<T>>;\r\n#define\
    \ rep(i,n) for(int i=0;i<(int)(n);i++)\r\n#define rep1(i,n) for(int i=1;i<=(int)(n);i++)\r\
    \n#define per(i,n) for(int i=(int)(n)-1;0<=i;i--)\r\n#define per1(i,n) for(int\
    \ i=(int)(n);0<i;i--)\r\n#define range(i,x) for(auto&i:x)\r\n#define range2(i,j,x)\
    \ for(auto&[i,j]:x)\r\n#define all(x) (x).begin(),(x).end()\r\n#define rall(x)\
    \ (x).rbegin(),(x).rend()\r\n#define Sort(x) sort((x).begin(),(x).end())\r\n#define\
    \ troS(x) sort((x).rbegin(),(x).rend())\r\n#define Reverse(x) reverse((x).begin(),(x).end())\r\
    \n#define uniq(x) sort((x).begin(),(x).end());(x).erase(unique((x).begin(),(x).end()),(x).end())\r\
    \n#define nextp(x) next_permutation((x).begin(),(x).end())\r\n#define nextc(x,k)\
    \ next_combination((x).begin(),(x).end(),k)\r\n#define bit(x,i) (((x)>>(i))&1)\r\
    \n#define pf push_front\r\n#define pb push_back\r\n#define df pop_front\r\n#define\
    \ db pop_back\r\n#define fi first\r\n#define se second\r\n#define elif else if\r\
    \n#define Yes cout<<\"Yes\"<<'\\n'\r\n#define No cout<<\"No\"<<'\\n'\r\n#define\
    \ YN(x) cout<<((x)?\"Yes\":\"No\")<<'\\n'\r\n#define O(x) cout<<(x)<<'\\n'\r\n\
    template<class S,class T>bool chmin(S&a,T b){if(a>b){a=b;return true;}return false;}\r\
    \ntemplate<class S,class T>bool chmax(S&a,T b){if(a<b){a=b;return true;}return\
    \ false;}\r\ntemplate<class S,class T,class U>bool ismid(S a,S b,S c){return a<=b&&b<c;}\r\
    \ntemplate<class T>bool next_combination(T l,T r,int k){T m=l+k;if(l==r||l==m||r==m)return\
    \ false;T t=m;while(l!=t){t--;if(*t<*(r-1)){T d=m;while(*t>=*d)d++;iter_swap(t,d);rotate(t+1,d+1,r);rotate(m,m+(r-d)-1,r);return\
    \ true;}}rotate(l,m,r);return false;}\r\ntemplate<class T>T Min(T a,T b){return\
    \ a<b?a:b;}\r\ntemplate<class T,class...Args>T Min(T a,T b,Args...args){return\
    \ Min(Min(a,b),args...);}\r\ntemplate<class T>T Max(T a,T b){return a>b?a:b;}\r\
    \ntemplate<class T,class...Args>T Max(T a,T b,Args...args){return Max(Max(a,b),args...);}\r\
    \ntemplate<class T>T Sum(T a){return a;}\r\ntemplate<class T,class... Args>T Sum(T\
    \ a,Args... args){return a+Sum(args...);}\r\ntemplate<class T>T Max(const vector<T>&v){return\
    \ *max_element(all(v));}\r\ntemplate<class T>T Min(const vector<T>&v){return *min_element(all(v));}\r\
    \ntemplate<class T>T Sum(const vector<T>&v){return accumulate(all(v),T(0));}\r\
    \ntemplate<class S,class T>T Max(const pair<S,T>&p){return max(p.first,p.second);}\r\
    \ntemplate<class S,class T>T Min(const pair<S,T>&p){return min(p.first,p.second);}\r\
    \ntemplate<class S,class T>T Sum(const pair<S,T>&p){return p.first+p.second;}\r\
    \ntemplate<class S,class T>istream&operator>>(istream&s,pair<S,T>&p){s>>p.first>>p.second;return\
    \ s;}\r\ntemplate<class S,class T>ostream&operator<<(ostream&s,pair<S,T>&p){s<<p.first<<'\
    \ '<<p.second<<'\\n';return s;}\r\ntemplate<class T>istream&operator>>(istream&s,vector<T>&v){for(auto&i:v)s>>i;return\
    \ s;}\r\ntemplate<class T>ostream&operator<<(ostream&s,vector<T>&v){for(auto&i:v)s<<i<<'\
    \ ';s<<'\\n';return s;}\r\ntemplate<class F>long long bsearch(long long ok,long\
    \ long ng,F&f){while(abs(ok-ng)>1){long long mid=(ok+ng)/2;if(f(mid))ok=mid;else\
    \ ng=mid;}return ok;}\r\nconst int dxy[5]={0,1,0,-1,0};\r\nconst int dx[8]={0,1,0,-1,1,1,-1,-1};\r\
    \nconst int dy[8]={1,0,-1,0,1,-1,1,-1};\r\n#define nl '\\n'\r\n#define sp ' '\r\
    \n#define inf ((1<<30)-(1<<15))\r\n#define INF (1LL<<61)\r\n#define mod 998244353\r\
    \n#line 3 \"structure/sparsetable.hpp\"\nusing namespace std;\n// op(op(a, b),\
    \ b) = op(a, b) \u304C\u6210\u308A\u7ACB\u3064\u5FC5\u8981\u304C\u3042\u308B(\u51AA\
    \u7B49\u6027)\ntemplate<class T, auto op>\nstruct sparsetable {\n    int n;\n\
    \    vector<vector<T>> data;\n    // sparsetable \u3092\u69CB\u7BC9 O(n log n)\n\
    \    sparsetable(const vector<T>& v) : n(v.size()) {\n        int m = 1;\n   \
    \     while (m < n) m <<= 1;\n        data.assign(m, vector<T>(__lg(m)+1));\n\
    \        for (int i=0; i<n; i++) data[i][0] = v[i];\n        for (int j=1; j<=__lg(m);\
    \ j++) {\n            for (int i=0; i+(1<<j)<=n; i++) {\n                data[i][j]\
    \ = op(data[i][j-1], data[i+(1<<(j-1))][j-1]);\n            }\n        }\n   \
    \ }\n    // op([l, r)) \u306E\u5024\u3092\u53D6\u5F97 O(1)\n    T prod(int l,\
    \ int r) {\n        assert(0 <= l && l <= r && r <= n);\n        if (l == r) return\
    \ T{};\n        int j = __lg(r-l);\n        return op(data[l][j], data[r-(1 <<\
    \ j)][j]);\n    }\n};\n#line 82 \"verify/yosupo-staticrmq.test.cpp\"\n\r\nvoid\
    \ solve();\r\nint main() {\r\n    ios::sync_with_stdio(false);\r\n    cin.tie(nullptr);\r\
    \n    cout<<fixed<<setprecision(30);\r\n    int T=1;\r\n    // cin >> T;\r\n \
    \   while (T--) solve();\r\n}\r\n\r\nvoid solve() {\r\n    int n, q;\r\n    cin\
    \ >> n >> q;\r\n    vi a(n);\r\n    cin >> a;\r\n    sparsetable<int, [](int a,\
    \ int b) { return min(a, b); }> st(a);\r\n    while (q--) {\r\n        int l,\
    \ r;\r\n        cin >> l >> r;\r\n        cout << st.prod(l, r) << nl;\r\n   \
    \ }\r\n}\n"
  code: "#define PROBLEM \"https://judge.yosupo.jp/problem/staticrmq\"\r\n#ifdef poe\r\
    \n#define debug(x) cerr<<#x<<\": \"<<x<<endl\r\n#else\r\n#define debug(x)\r\n\
    // #pragma GCC target(\"arch=skylake-avx512\")\r\n// #pragma GCC target(\"avx2\"\
    )\r\n// #pragma GCC optimize(\"O3\")\r\n// #pragma GCC optimize(\"unroll-loops\"\
    )\r\n#endif\r\n#include<bits/stdc++.h>\r\nusing namespace std;\r\nusing ll=long\
    \ long;\r\nusing ull=unsigned long long;\r\nusing ld=long double;\r\nusing pi=pair<int,int>;\r\
    \nusing pll=pair<ll,ll>;\r\nusing str=string;\r\ntemplate<class T>using vec=vector<T>;\r\
    \nusing vi=vec<int>;using vvi=vec<vi>;using vvvi=vec<vvi>;using vvvvi=vec<vvvi>;using\
    \ vvvvvi=vec<vvvvi>;\r\nusing vll=vec<ll>;using vvll=vec<vll>;using vvvll=vec<vvll>;using\
    \ vvvvll=vec<vvvll>;using vvvvvll=vec<vvvvll>;\r\nusing vpi=vec<pi>;using vvpi=vec<vpi>;using\
    \ vvvpi=vec<vvpi>;using vvvvpi=vec<vvvpi>;using vvvvvpi=vec<vvvvpi>;\r\nusing\
    \ vpll=vec<pll>;using vvpll=vec<vpll>;using vvvpll=vec<vvpll>;using vvvvpll=vec<vvvpll>;using\
    \ vvvvvpll=vec<vvvvpll>;\r\ntemplate<class T>using pq=priority_queue<T,vector<T>>;\r\
    \ntemplate<class T>using pqg=priority_queue<T,vector<T>,greater<T>>;\r\n#define\
    \ rep(i,n) for(int i=0;i<(int)(n);i++)\r\n#define rep1(i,n) for(int i=1;i<=(int)(n);i++)\r\
    \n#define per(i,n) for(int i=(int)(n)-1;0<=i;i--)\r\n#define per1(i,n) for(int\
    \ i=(int)(n);0<i;i--)\r\n#define range(i,x) for(auto&i:x)\r\n#define range2(i,j,x)\
    \ for(auto&[i,j]:x)\r\n#define all(x) (x).begin(),(x).end()\r\n#define rall(x)\
    \ (x).rbegin(),(x).rend()\r\n#define Sort(x) sort((x).begin(),(x).end())\r\n#define\
    \ troS(x) sort((x).rbegin(),(x).rend())\r\n#define Reverse(x) reverse((x).begin(),(x).end())\r\
    \n#define uniq(x) sort((x).begin(),(x).end());(x).erase(unique((x).begin(),(x).end()),(x).end())\r\
    \n#define nextp(x) next_permutation((x).begin(),(x).end())\r\n#define nextc(x,k)\
    \ next_combination((x).begin(),(x).end(),k)\r\n#define bit(x,i) (((x)>>(i))&1)\r\
    \n#define pf push_front\r\n#define pb push_back\r\n#define df pop_front\r\n#define\
    \ db pop_back\r\n#define fi first\r\n#define se second\r\n#define elif else if\r\
    \n#define Yes cout<<\"Yes\"<<'\\n'\r\n#define No cout<<\"No\"<<'\\n'\r\n#define\
    \ YN(x) cout<<((x)?\"Yes\":\"No\")<<'\\n'\r\n#define O(x) cout<<(x)<<'\\n'\r\n\
    template<class S,class T>bool chmin(S&a,T b){if(a>b){a=b;return true;}return false;}\r\
    \ntemplate<class S,class T>bool chmax(S&a,T b){if(a<b){a=b;return true;}return\
    \ false;}\r\ntemplate<class S,class T,class U>bool ismid(S a,S b,S c){return a<=b&&b<c;}\r\
    \ntemplate<class T>bool next_combination(T l,T r,int k){T m=l+k;if(l==r||l==m||r==m)return\
    \ false;T t=m;while(l!=t){t--;if(*t<*(r-1)){T d=m;while(*t>=*d)d++;iter_swap(t,d);rotate(t+1,d+1,r);rotate(m,m+(r-d)-1,r);return\
    \ true;}}rotate(l,m,r);return false;}\r\ntemplate<class T>T Min(T a,T b){return\
    \ a<b?a:b;}\r\ntemplate<class T,class...Args>T Min(T a,T b,Args...args){return\
    \ Min(Min(a,b),args...);}\r\ntemplate<class T>T Max(T a,T b){return a>b?a:b;}\r\
    \ntemplate<class T,class...Args>T Max(T a,T b,Args...args){return Max(Max(a,b),args...);}\r\
    \ntemplate<class T>T Sum(T a){return a;}\r\ntemplate<class T,class... Args>T Sum(T\
    \ a,Args... args){return a+Sum(args...);}\r\ntemplate<class T>T Max(const vector<T>&v){return\
    \ *max_element(all(v));}\r\ntemplate<class T>T Min(const vector<T>&v){return *min_element(all(v));}\r\
    \ntemplate<class T>T Sum(const vector<T>&v){return accumulate(all(v),T(0));}\r\
    \ntemplate<class S,class T>T Max(const pair<S,T>&p){return max(p.first,p.second);}\r\
    \ntemplate<class S,class T>T Min(const pair<S,T>&p){return min(p.first,p.second);}\r\
    \ntemplate<class S,class T>T Sum(const pair<S,T>&p){return p.first+p.second;}\r\
    \ntemplate<class S,class T>istream&operator>>(istream&s,pair<S,T>&p){s>>p.first>>p.second;return\
    \ s;}\r\ntemplate<class S,class T>ostream&operator<<(ostream&s,pair<S,T>&p){s<<p.first<<'\
    \ '<<p.second<<'\\n';return s;}\r\ntemplate<class T>istream&operator>>(istream&s,vector<T>&v){for(auto&i:v)s>>i;return\
    \ s;}\r\ntemplate<class T>ostream&operator<<(ostream&s,vector<T>&v){for(auto&i:v)s<<i<<'\
    \ ';s<<'\\n';return s;}\r\ntemplate<class F>long long bsearch(long long ok,long\
    \ long ng,F&f){while(abs(ok-ng)>1){long long mid=(ok+ng)/2;if(f(mid))ok=mid;else\
    \ ng=mid;}return ok;}\r\nconst int dxy[5]={0,1,0,-1,0};\r\nconst int dx[8]={0,1,0,-1,1,1,-1,-1};\r\
    \nconst int dy[8]={1,0,-1,0,1,-1,1,-1};\r\n#define nl '\\n'\r\n#define sp ' '\r\
    \n#define inf ((1<<30)-(1<<15))\r\n#define INF (1LL<<61)\r\n#define mod 998244353\r\
    \n#include \"sparsetable\"\r\n\r\nvoid solve();\r\nint main() {\r\n    ios::sync_with_stdio(false);\r\
    \n    cin.tie(nullptr);\r\n    cout<<fixed<<setprecision(30);\r\n    int T=1;\r\
    \n    // cin >> T;\r\n    while (T--) solve();\r\n}\r\n\r\nvoid solve() {\r\n\
    \    int n, q;\r\n    cin >> n >> q;\r\n    vi a(n);\r\n    cin >> a;\r\n    sparsetable<int,\
    \ [](int a, int b) { return min(a, b); }> st(a);\r\n    while (q--) {\r\n    \
    \    int l, r;\r\n        cin >> l >> r;\r\n        cout << st.prod(l, r) << nl;\r\
    \n    }\r\n}"
  dependsOn:
  - structure/sparsetable.hpp
  isVerificationFile: true
  path: verify/yosupo-staticrmq.test.cpp
  requiredBy: []
  timestamp: '2025-03-31 12:21:05+09:00'
  verificationStatus: TEST_ACCEPTED
  verifiedWith: []
documentation_of: verify/yosupo-staticrmq.test.cpp
layout: document
redirect_from:
- /verify/verify/yosupo-staticrmq.test.cpp
- /verify/verify/yosupo-staticrmq.test.cpp.html
title: verify/yosupo-staticrmq.test.cpp
---
