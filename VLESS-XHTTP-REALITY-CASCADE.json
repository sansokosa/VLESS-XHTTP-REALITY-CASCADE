{
  "log": {
    "loglevel": "warning"
  },
  "dns": {
    "hosts": {
      "common.dot.dns.yandex.net": [
        "77.88.8.8",
        "77.88.8.1"
      ]
    },
    "servers": [
      {
        "address": "https://common.dot.dns.yandex.net/dns-query",
        "domains": [
          "geosite:category-gov-ru",
          "regexp:.*\\.ru$",
          "regexp:.*\\.рф$",
          "regexp:.*\\.xn--p1ai$",
          "regexp:.*\\.su$",
          "domain:yandex.net",
          "domain:yandex.com",
          "domain:vk.com",
          "domain:vk.me",
          "domain:mail.ru"
        ],
        "skipFallback": true
      },
      {
        "address": "https://8.8.8.8/dns-query",
        "domains": [
          "geosite:geolocation-!cn"
        ],
        "skipFallback": true
      },
      "https://1.1.1.1/dns-query"
    ],
    "queryStrategy": "UseIPv4"
  },
  "inbounds": [
    {
      "tag": "PUBLIC_RU_INBOUND",
      "port": 443,
      "listen": "0.0.0.0",
      "protocol": "vless",
      "settings": {
        "clients": [],
        "decryption": "none"
      },
      "sniffing": {
        "enabled": true,
        "routeOnly": false,
        "destOverride": [
          "http",
          "tls",
          "quic"
        ],
        "metadataOnly": false
      },
      "streamSettings": {
        "network": "xhttp",
        "sockopt": {
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 30
        },
        "security": "reality",
        "xhttpSettings": {
          "host": "YOUR_DOMAIN",
          "mode": "auto",
          "path": "/api",
          "xPaddingBytes": "100-1000",
          "scStreamUpServerSecs": "30-90"
        },
        "realitySettings": {
          "show": false,
          "xver": 2,
          "target": "YOUR_IP:(9)443",
          "shortIds": [
            "YOUR_ID"
          ],
          "privateKey": "YOUR_KEY",
          "serverNames": [
            "YOUR_DOMAIN"
          ]
        }
      }
    }
  ],
  "outbounds": [
    {
      "tag": "DIRECT",
      "protocol": "freedom",
      "settings": {
        "domainStrategy": "UseIPv4"
      }
    },
    {
      "tag": "VLESS_OUTBOUND_TO_DE",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "port": 9999,
            "users": [
              {
                "id": "BRIDGE_USER_VLESS_ID",
                "flow": "xtls-rprx-vision",
                "encryption": "none"
              }
            ],
            "address": "YOUR_IP"
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "sockopt": {
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 30
        },
        "security": "reality",
        "realitySettings": {
          "shortId": "YOUR_ID",
          "spiderX": "/",
          "publicKey": "YOUR_KEY",
          "serverName": "YOUR_DOMAIN",
          "fingerprint": "firefox"
        }
      }
    },
    {
      "tag": "BLOCK",
      "protocol": "blackhole",
      "settings": {
        "response": {
          "type": "http"
        }
      }
    }
  ],
  "routing": {
    "rules": [
      {
        "ip": [
          "geoip:private",
          "127.0.0.0/8",
          "::1/128",
          "fc00::/7",
          "fe80::/10",
          "geoip:ru",
          "155.133.224.0/19",
          "185.25.180.0/22",
          "190.217.33.0/24",
          "162.254.192.0/21",
          "205.196.6.0/24",
          "208.64.200.0/22",
          "208.78.164.0/22",
          "103.10.124.0/23",
          "103.28.54.0/24",
          "146.66.152.0/21",
          "185.25.182.0/23",
          "192.69.96.0/22",
          "213.171.36.0/24"
        ],
        "type": "field",
        "_Comment": "DIRECT: LAN/private/RU/Valve",
        "outboundTag": "DIRECT"
      },
      {
        "type": "field",
        "domain": [
          "regexp:.*\\.ru$",
          "regexp:.*\\.рф$",
          "regexp:.*\\.xn--p1ai$",
          "regexp:.*\\.su$",
          "geosite:category-gov-ru",
          "domain:livejournal.com",
          "domain:nalog.ru",
          "domain:yandex.net",
          "domain:yandex.com",
          "domain:yastatic.net",
          "domain:vk.com",
          "domain:vk.me",
          "domain:mail.ru",
          "domain:ok.ru",
          "domain:dzen.ru",
          "domain:dion.vc",
          "domain:dion.ru",
          "domain:mts.ru",
          "domain:megafon.ru",
          "domain:beeline.ru",
          "domain:tele2.ru",
          "domain:rt.ru",
          "domain:steamserver.net",
          "domain:steamcontent.com",
          "domain:steamstatic.com",
          "domain:steampowered.com",
          "domain:steam-chat.com",
          "domain:steamgames.com",
          "domain:steamusercontent.com",
          "domain:valve.net",
          "domain:valvesoftware.com",
          "domain:csgo.wmsj.cn",
          "domain:dota2.com",
          "domain:dotabuff.com",
          "domain:epicgames.com",
          "domain:unrealengine.com",
          "domain:fortnite.com",
          "domain:easyanticheat.net",
          "domain:easy.ac",
          "domain:riotgames.com",
          "domain:riotcdn.net",
          "domain:leagueoflegends.com",
          "domain:battle.net",
          "domain:blizzard.com",
          "domain:blz-contentstack.com",
          "domain:ea.com",
          "domain:origin.com",
          "domain:tnt-ea.com",
          "domain:ubisoft.com",
          "domain:ubi.com",
          "domain:uplay.com",
          "domain:faceit.com",
          "domain:faceit-cdn.net",
          "domain:gaijin.net",
          "domain:warthunder.com",
          "domain:wargaming.net",
          "domain:supercell.com",
          "domain:mihoyo.com",
          "domain:hoyoverse.com",
          "domain:hoyolab.com",
          "domain:rockstargames.com",
          "domain:socialclub.rockstargames.com",
          "domain:minecraft.net",
          "domain:hitmos.fm",
          "domain:mojang.com"
        ],
        "_Comment": "DIRECT: RU + игры",
        "outboundTag": "DIRECT"
      },
      {
        "ip": [
          "8.8.8.8",
          "8.8.4.4",
          "1.1.1.1",
          "1.0.0.1"
        ],
        "type": "field",
        "_Comment": "TUNNEL: зарубежный DoH уводим через выход (иначе уйдёт DIRECT по умолчанию)",
        "outboundTag": "VLESS_OUTBOUND_TO_DE"
      },
      {
        "port": "25,465,587",
        "type": "field",
        "network": "tcp",
        "_Comment": "BLOCK: SMTP",
        "outboundTag": "BLOCK"
      },
      {
        "type": "field",
        "_Comment": "BLOCK: BitTorrent",
        "protocol": [
          "bittorrent"
        ],
        "outboundTag": "BLOCK"
      },
      {
        "port": "6881-6999,51413,4444,4662,4672,1337,2710",
        "type": "field",
        "_Comment": "BLOCK: торрент-порты",
        "outboundTag": "BLOCK"
      },
      {
        "port": "119,563",
        "type": "field",
        "network": "tcp",
        "_Comment": "BLOCK: Usenet NNTP",
        "outboundTag": "BLOCK"
      },
      {
        "type": "field",
        "domain": [
          "regexp:.*tracker.*\\..*",
          "regexp:.*\\.torrent$",
          "domain:openbittorrent.com",
          "domain:opentrackr.org",
          "domain:coppersurfer.tk",
          "domain:leechers-paradise.org",
          "domain:zer0day.ch",
          "domain:explodie.org",
          "domain:demonii.si",
          "domain:exodus.desync.com",
          "domain:p2p.0g.cx",
          "domain:dht.transmissionbt.com",
          "domain:router.bittorrent.com",
          "domain:router.utorrent.com",
          "domain:dht.libtorrent.org",
          "domain:rarbg.to",
          "domain:1337x.to",
          "domain:thepiratebay.org",
          "domain:nyaa.si",
          "domain:rutracker.org",
          "domain:rutor.info",
          "domain:kinozal.tv",
          "domain:nnmclub.to"
        ],
        "_Comment": "BLOCK: трекеры",
        "outboundTag": "BLOCK"
      },
      {
        "type": "field",
        "domain": [
          "geosite:category-ads-all"
        ],
        "_Comment": "BLOCK: реклама (префильтр)",
        "outboundTag": "BLOCK"
      },
      {
        "type": "field",
        "network": "tcp,udp",
        "_Comment": "CATCH-ALL: Всё остальное (TCP+UDP) → через DE",
        "inboundTag":
          "PUBLIC_RU_INBOUND"
        ],
        "outboundTag": "VLESS_OUTBOUND_TO_DE"
      }
    ],
    "domainMatcher": "mph",
    "domainStrategy": "IPIfNonMatch"
  }
}
