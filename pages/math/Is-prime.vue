<template>
    <v-container>
        <v-row no-gutters>

            <v-col cols="12" class="my-5">
                <h1>Is prime(素数判定)</h1>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>概要</h2>
                <v-container>
                    <p>
                        素数かどうかを判定します。
                    </p>
                    <p class="pl-3">
                        - IsPrime(n) : nが素数かどうか判定する
                    </p>
                </v-container>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>計算量</h2>
                <v-container>
                    <p>
                        - IsPrime : O(sqrt(n))
                    </p>
                </v-container>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>コード</h2>
                <v-container>
                    <pre v-highlightjs class="align-center">
                    <code class="cpp">
                        bool IsPrime(int n) {
                            if(n < 2) return false;
                            else if(n == 2) return true;
                            else if(n % 2==0) return false;
                            double sqrtNum = sqrt(n);
                            for(int i = 3; i <= sqrtNum; i += 2) {
                                if(n % i == 0) {
                                    return false;
                                }
                            }
                            return true;
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
