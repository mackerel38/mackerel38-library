---
data:
  _extendedDependsOn:
  - icon: ':heavy_check_mark:'
    path: structure/UnionFind.hpp
    title: structure/UnionFind.hpp
  _extendedRequiredBy: []
  _extendedVerifiedWith: []
  _isVerificationFailed: false
  _pathExtension: cpp
  _verificationStatusIcon: ':heavy_check_mark:'
  attributes:
    '*NOT_SPECIAL_COMMENTS*': ''
    PROBLEM: https://judge.u-aizu.ac.jp/onlinejudge/description.jsp?id=DSL_1_A
    links:
    - https://judge.u-aizu.ac.jp/onlinejudge/description.jsp?id=DSL_1_A
  bundledCode: "#line 1 \"verify/aizu-DSL_1_A.test.cpp\"\n#define PROBLEM \"https://judge.u-aizu.ac.jp/onlinejudge/description.jsp?id=DSL_1_A\"\
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
    \n#line 3 \"structure/UnionFind.hpp\"\nusing namespace std;\nstruct UnionFind\
    \ {\n    int n;\n    vector<int> data;\n    // n \u500B\u306E\u8981\u7D20\u304B\
    \u3089\u306A\u308BUnionFind \u3092\u69CB\u7BC9 O(n)\n    UnionFind(int _n) : n(_n),\
    \ data(_n, -1) {}\n    // 2 \u3064\u306E\u8981\u7D20\u3092\u4F75\u5408 O(\u03B1\
    (n))\n    bool merge(int p, int q) {\n        p = root(p);\n        q = root(q);\n\
    \        if (p == q) return false;\n        if (q < p) swap(p, q);\n        data[p]\
    \ += data[q];\n        data[q] = p;\n        return true;\n    }\n    // \u89AA\
    \u8981\u7D20\u3092\u53D6\u5F97 O(\u03B1(n))\n    int root(int p) {\n        assert(0\
    \ <= p && p < n);\n        if (data[p] < 0) {\n            return p;\n       \
    \ } else {\n            data[p] = root(data[p]);\n            return data[p];\n\
    \        }\n    }\n    // \u89AA\u8981\u7D20\u3092\u53D6\u5F97 O(\u03B1(n))\n\
    \    int operator[](int p) {\n        return root(p);\n    }\n    // 2 \u3064\u306E\
    \u8981\u7D20\u304C\u540C\u3058\u96C6\u5408\u306B\u542B\u307E\u308C\u308B\u304B\
    \u5224\u5B9A O(\u03B1(n))\n    bool same(int p, int q) {\n        return root(p)\
    \ == root(q);\n    }\n    // \u8981\u7D20\u304C\u5C5E\u3059\u308B\u96C6\u5408\u306E\
    \u5927\u304D\u3055\u3092\u8FD4\u3059 O(\u03B1(n))\n    int size(int p) {\n   \
    \     return -data[root(p)];\n    }\n    // UnionFind \u306E\u9023\u7D50\u6210\
    \u5206\u306Evector \u3092\u8FD4\u3059 O(n\u03B1(n))\n    vector<vector<int>> groups()\
    \ {\n        vector<vector<int>> re(n);\n        for (int i=0; i<n; i++) re[root(i)].push_back(i);\n\
    \        re.erase(remove_if(re.begin(), re.end(), [](vector<int>& v){ return v.empty();\
    \ }), re.end());\n        return re;\n    }\n};\n#line 82 \"verify/aizu-DSL_1_A.test.cpp\"\
    \n\r\nvoid solve();\r\nint main() {\r\n    ios::sync_with_stdio(false);\r\n  \
    \  cin.tie(nullptr);\r\n    cout<<fixed<<setprecision(30);\r\n    int T=1;\r\n\
    \    // cin >> T;\r\n    while (T--) solve();\r\n}\r\n\r\nvoid solve() {\r\n \
    \   int n, q; cin >> n >> q;\r\n    UnionFind uf(n);\r\n    while (q--) {\r\n\
    \        int x, y, z; cin >> x >> y >> z;\r\n        if (x == 0) {\r\n       \
    \     uf.merge(y, z);\r\n        } else {\r\n            cout << uf.same(y, z)\
    \ << nl;\r\n        }\r\n    }\r\n}\n"
  code: "#define PROBLEM \"https://judge.u-aizu.ac.jp/onlinejudge/description.jsp?id=DSL_1_A\"\
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
    \n#include \"UnionFind\"\r\n\r\nvoid solve();\r\nint main() {\r\n    ios::sync_with_stdio(false);\r\
    \n    cin.tie(nullptr);\r\n    cout<<fixed<<setprecision(30);\r\n    int T=1;\r\
    \n    // cin >> T;\r\n    while (T--) solve();\r\n}\r\n\r\nvoid solve() {\r\n\
    \    int n, q; cin >> n >> q;\r\n    UnionFind uf(n);\r\n    while (q--) {\r\n\
    \        int x, y, z; cin >> x >> y >> z;\r\n        if (x == 0) {\r\n       \
    \     uf.merge(y, z);\r\n        } else {\r\n            cout << uf.same(y, z)\
    \ << nl;\r\n        }\r\n    }\r\n}"
  dependsOn:
  - structure/UnionFind.hpp
  isVerificationFile: true
  path: verify/aizu-DSL_1_A.test.cpp
  requiredBy: []
  timestamp: '2025-03-31 14:46:06+09:00'
  verificationStatus: TEST_ACCEPTED
  verifiedWith: []
documentation_of: verify/aizu-DSL_1_A.test.cpp
layout: document
redirect_from:
- /verify/verify/aizu-DSL_1_A.test.cpp
- /verify/verify/aizu-DSL_1_A.test.cpp.html
title: verify/aizu-DSL_1_A.test.cpp
---
