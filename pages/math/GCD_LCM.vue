<template>
    <v-container>
        <v-row no-gutters>

            <v-col cols="12" class="my-5">
                <h1>GCD(最大公約数), LCM(最小公倍数)</h1>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>概要</h2>
                <v-container>
                    <p>
                        最大公約数, 最小公倍数を求めます。
                    </p>
                    <p class="pl-3">
                        - GCD(x, y) : xとyの最大公約数を求める
                    </p>
                    <p class="pl-3">
                        - LCM(x, y) : xとyの最小公倍数を求める
                    </p>
                </v-container>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>計算量</h2>
                <v-container>
                    <p>
                        - GCD : O(log min(x, y))
                    </p>
                    <p>
                        - LCM : O(log min(x, y))
                    </p>
                </v-container>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>コード</h2>
                <v-container>
                    <pre v-highlightjs class="align-center">
                    <code class="cpp">
                        long long GCD(long long x, long long y) {
                            if(y == 0) return x;
                            return GCD(y, x % y);
                        }

                        long long LCM(long long x, long long y) {
                            return x * y / GCD(x, y);
                        }
                    </code>
                </pre>
                </v-container>
            </v-col>

            <v-col cols="12">
                <h2>Verified with</h2>
                <v-container>
                    <h3>GCD</h3>
                    <p class="pl-3">
                        - Problem : <a href="https://judge.u-aizu.ac.jp/onlinejudge/description.jsp?id=ALDS1_1_B" target="_blank" rel="noopener noreferrer">AOJ - Greatest Common Divisor</a>
                    </p>
                    <pre v-highlightjs class="align-center">
                    <code class="cpp">
                        #include&lt;bits/stdc++.h&gt;
                        using namespace std;

                        long long GCD(long long x, long long y) {
                            if(y == 0) return x;
                            return GCD(y, x % y);
                        }

                        int main()
                        {
                            long long x, y;
                            cin >> x >> y;
                            cout << GCD(x, y) << endl;
                            return 0;
                        }
                    </code>
                    </pre>
                    <h3>LCM</h3>
                    <p class="pl-3">
                        - Problem : <a href="https://judge.u-aizu.ac.jp/onlinejudge/description.jsp?id=NTL_1_C" target="_blank" rel="noopener noreferrer">AOJ - Least Common Multiple</a>
                    </p>
                    <pre v-highlightjs>
                    <code class="cpp">
                        #include&lt;bits/stdc++.h&gt;
                        using namespace std;

                        long long GCD(long long x, long long y) {
                            if(y == 0) return x;
                            return GCD(y, x % y);
                        }

                        long long LCM(long long x, long long y) {
                            return x * y / GCD(x, y);
                        }

                        int main()
                        {
                            int n;
                            cin >> n;
                            long long ans = 1;
                            for(int i = 0; i < n; i++) {
                                long long x;
                                cin >> x;
                                ans = LCM(ans, x);
                            }
                            cout << ans << endl;
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
