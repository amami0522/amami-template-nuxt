<template>
    <v-container>
        <v-row no-gutters>

            <v-col cols="12" class="my-5">
                <h1>Bellman ford(単一始点最短路)</h1>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>概要</h2>
                <v-container>
                    <p>
                        単一始点の最短路を求めます。
                        負の重みを持つ辺にも対応しています。
                    </p>
                    <p class="pl-3">
                        - bellman_ford(edges, V, s) : 辺の集合edgesより, 頂点数Vの時の頂点sからの各頂点への最短路を求める。
                    </p>
                </v-container>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>計算量</h2>
                <v-container>
                    <p>
                        - bellman_ford(edges, V, s) : O(V|edges|)
                    </p>
                </v-container>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>コード</h2>
                <v-container>
                    <pre v-highlightjs class="align-center">
                    <code class="cpp">
                        template&lt;typename T&gt;
                        struct edge{
                            long long src;
                            long long to;
                            T cost;
                        };

                        template&lt;typename T&gt;
                        using Edges = vector&lt;edge&lt;T&gt;&gt;;

                        template&lt;typename T&gt;
                        vector&lt;T&gt; bellman_ford(Edges&lt;T&gt; &edges, int V, int s) {
                            vector&lt;T&gt; dist(V, INF);
                            dist[s] = 0;
                            for(int i = 0; i &lt; V - 1; i++) {
                                for(auto& e : edges) {
                                    if(dist[e.src] == INF) continue;
                                    dist[e.to] = min(dist[e.to], dist[e.src] + e.cost);
                                }
                            }
                            for(auto& e : edges) {
                                if(dist[e.src] == INF) continue;
                                if(dist[e.src] + e.cost &lt; dist[e.to]) return vector&lt;T&gt;();
                            }
                            return dist;
                        }
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
