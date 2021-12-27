<template>
    <v-container>
        <v-row no-gutters>

            <v-col cols="12" class="my-5">
                <h1>Union Find(素集合)</h1>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>概要</h2>
                <v-container>
                    <p>
                        素集合を扱うデータ構造です。
                    </p>
                    <p class="pl-3">
                        - unite(x, y) : ノードxとyを同集合とする<br>
                        - same(x, y) : ノードxとyが同集合内かを判定する<br>
                        - root(x) : ノードxの根を求める<br>
                        - size(x) : ノードxが含まれる集合のサイズを求める<br>
                    </p>
                </v-container>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>計算量</h2>
                <v-container>
                    <p>
                        - unite(x, y) : O()<br>
                        - same(x, y) : O()<br>
                        - root(x) : O()<br>
                        - size(x) : O(1)<br>
                    </p>
                </v-container>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>コード</h2>
                <v-container>
                    <pre v-highlightjs class="align-center">
                    <code class="cpp">
                        struct UnionFind {
                            vector&lt;long long&gt; par;
                            UnionFind(long long size) : par(size + 1, -1) {}
                            bool unite(long long x, long long y) {
                                x = root(x);
                                y = root(y);
                                if(x != y) {
                                    if(par[y] &lt; par[x]) swap(x, y);
                                    par[x] += par[y];
                                    par[y] = x;
                                }
                                return x != y;
                            }
                            bool same(long long x, long long y) {
                                return root(x) == root(y);
                            }
                            int root(long long x) {
                                return par[x] &lt; 0 ? x : par[x] = root(par[x]);
                            }
                            int size(long long x) {
                                return -par[root(x)];
                            }
                        };
                    </code>
                </pre>
                </v-container>
            </v-col>

            <v-col cols="12">
                <h2>Verified with</h2>
                <v-container>
                    <p>
                        - Problem : <a href="Prime Factorize">AOJ - Prime Factorize</a>
                    </p>
                    <pre v-highlightjs class="align-center">
                    <code class="cpp">
                        #include&lt;bits/stdc++.h&gt;
                        using namespace std;

                        map&lt;long long, int&gt; prime_factor(long long n) {
                            map&lt;long long, int&gt; ret;
                            for(long long i = 2; i * i <= n; i++) {
                                while(n % i == 0) {
                                    ret[i]++;
                                    n /= i;
                                }
                            }
                            if(n != 1) ret[n] = 1;
                            return ret;
                        }

                        int main()
                        {
                            long long n;
                            cin >> n;
                            cout << n << ":";
                            for(auto&& [p, k] : prime_factor(n)) {
                                while(k--) cout << " " << p;
                            }
                            cout << endl;
                            return 0;
                        }
                    </code>
                    </pre>
                </v-container>
            </v-col>

        </v-row>
    </v-container>
</template>

<script>
export default {
}
</script>

<style>
h1, h2, p {
    font-family: 'Noto Sans', 'Noto Sans JP', sans-serif;
}

a {
    text-decoration: none;
}

code {
    font-family: 'Source Code Pro';
}
</style>
