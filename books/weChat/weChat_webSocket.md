#### websocket

```js
  onShow: function() {
    let that = this;
    // 监听接收到socket消息
    that._onSocketMessageFunc();

    // 判断
    if (that.data.qrcode) {
      console.log('发送消息');
      wx.sendSocketMessage({
        data: 'success',
        success: function(res) {
          console.log(res, '发送成功');
        },
        fail: function(res) {
          console.log(res, '发送失败');
        }
      })
    }
  },

  onLoad: function() {
    //socket通信
    this._connectSocketFunc();
    this._onSocketErrorFunc();
    this._openSocketFunc();
  },

  // WebSocket 连接
  _connectSocketFunc() {
    wx.connectSocket({
      url: 'wss://wss.weixinxk.com/sk',
      header: {
        'content-type': 'application/json'
      },
      success(res) {
        console.log('connectSocket success', res);
      },
      fail(res) {
        console.log('connectSocket fail', res)
      }
    })
  },

  // WebSocket 监听 WebSocket 连接打开事件
  _openSocketFunc() {
    console.log('监听是否打开');
    let that = this;
    wx.onSocketOpen((res) => {
      console.log('open socke');
      openSocket = true;

      console.log('qrcode:', that.data.qrcode);
      if (that.data.qrcode) {

        console.log('发送消息');
        wx.sendSocketMessage({
          data: 'success',
          success: function(res) {

            console.log(res, '发送成功');
          },
          fail: function(res) {

            console.log(res, '发送失败');
          }
        })
      }
    })
  },

  _onSocketErrorFunc() {
    let that = this;
    // 监听socketError
    wx.onSocketError((res) => {
      console.log('socket 报错', res);
      setTimeout(() => {
        this._connectSocketFunc();
      }, 1000)
    })

    // 监听socket是否关闭
    wx.onSocketClose((res) => {
      console.log('关闭连接', res)
      setTimeout(() => {
        this._connectSocketFunc();
      }, 1000)
    })
  },

  // WebSocket 接收消息监听
  _onSocketMessageFunc() {
    let that = this;
    console.log('接收消息事件');
    wx.onSocketMessage((res) => {
      console.log('接收消息:', res.data);
      if (res.data == 'success') {

        that.setData({
          isLayer: false
        })
      }
    })
  },
```



