<template>
    <v-container>
        <v-row no-gutters>

            <v-col cols="12" class="my-5">
                <h1>Replace string(文字列置換)</h1>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>概要</h2>
                <v-container>
                    <p>
                        文字列中の特定の文字列を任意の文字列に変換します。
                    </p>
                    <p class="pl-3">
                        - replace_str(str, from, to) : strの中のfromをtoに置換する
                    </p>
                </v-container>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>計算量</h2>
                <v-container>
                    <p>
                        - replace_str : O(|str|)
                    </p>
                </v-container>
            </v-col>

            <v-col cols="12" class="ma-3">
                <h2>コード</h2>
                <v-container>
                    <pre v-highlightjs class="align-center">
                    <code class="cpp">
                        string replace_str(string &str, string from, string to) {
                            const unsigned int pos = str.find(from);
                            const int len = from.length();
                            if(pos == string::npos || from.empty()) return str;
                            return str.replace(pos, len, to);
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
