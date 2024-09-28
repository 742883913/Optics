<div align="center"><img src="cover2.png" width="800"></div>

<head>
  <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
  <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
      tex2jax: {
      skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
      inlineMath: [['$','$']]
      }
    });
  </script>
</head>

## Introduction

### Definitions

**Host（主机）**：网络中发送或接收数据的设备。

**Link（链路）**：连接网络设备的通信路径，传输数据。

**Switch（交换机）**：局域网中转发数据的设备，基于MAC地址转发。

**Protocol（协议）**：网络设备间通信的规则和标准，确保设备能够正确通信。

### Transmission method

1. **Unicast 单播** (point to point)
   应用场景：访问网页、发送电子邮件等等
2. **Broadcast 广播**
   特点：一对多传输，网络中的所有设备都能接受广播信息。
3. **Multicast 多播**
   特点：一对多传输，但仅限于加入了某个多播组的设备。多播高效地利用了网络带宽，因为它避免了单播时多次发送同样的数据。

### Host configuration

- Host configuration needs:
1. **a physical network cable**
2. **an IP address**
3. **a network mask(子网掩码)**：子网掩码用于区分IP地址的网络部分和主机部分，决定同一网络中的哪些主机可以直接通信。
4. **a gateway(网关)**：网关是网络中流量发送到其他子网的出入口，它的IP地址通常是与主机同一子网的路由器或交换机的IP地址。默认网关用于向其他子网或互联网发送数据包。
5. **a DNS server**