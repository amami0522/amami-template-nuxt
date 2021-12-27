<template>
    <v-container>
        <v-row no-gutters>

            <v-col cols="12" class="my-5">
                <h1>Prime factor(素因数分解)</h1>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>概要</h2>
                <v-container>
                    <p>
                        素因数分解した結果を求めます。
                    </p>
                    <p class="pl-3">
                        - prime_factor(n) : nを素因数分解する
                    </p>
                </v-container>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>計算量</h2>
                <v-container>
                    <p>
                        - prime_factor : O(sqrt(n))
                    </p>
                </v-container>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>コード</h2>
                <v-container>
                    <pre v-highlightjs class="align-center">
                    <code class="cpp">
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
