<template>
    <v-container>
        <v-row no-gutters>

            <v-col cols="12" class="my-5">
                <h1>Bit search(bit全探索)</h1>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>概要</h2>
                <v-container>
                    <p>
                        aaaaaaa
                    </p>
                    <p class="pl-3">
                        - bit_search(n) : n bitのbit全探索を行う
                    </p>
                </v-container>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>計算量</h2>
                <v-container>
                    <p>
                        - bit_search : O(2<sup>n</sup>)
                    </p>
                </v-container>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>コード</h2>
                <v-container>
                    <pre v-highlightjs class="align-center">
                    <code class="cpp">
                        void bit_search(int n) {
                            for(int bit = 0; bit &lt; (1 &lt;&lt; n); bit++) {
                                vector&lt;int&gt; v;
                                for(int i = 0; i &lt; n; i++) {
                                    if(bit & (1 &lt;&lt; i)) {
                                        // do something
                                    }
                                }
                            }
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
