<script>
import axios from 'axios';

// エンドポイントのベースとリクエストヘッダーをまとめてオブジェクト化して定数に代入
const client = axios.create({  //--1
  baseURL: 'https://github.com/AbdoulKamiss/todoproj.git', //--2
  headers: { //--3
    'Accept': 'application/vnd.github.v3+json',
    'Content-Type':'application/json',
    'Authorizathion': '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'
  },
})

export default {
//  省略
  methods: {
    getIssues() {
      // client定数からget()を呼び出し
      client.get('/issues') //--4
        .then((res) => {
          this.issues = res.data;
      })
    }
  }
}
</script>