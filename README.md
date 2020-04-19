# iplist
根据配置文件自动抓取IP列表

## 使用说明
### 使用方法
1. 根据.config.example复制一份.config文件到根目录
2. 修改配置文件为你需要的文件
3. 配合bs4爬虫即可输出想要抓取的IP段（库未公开）
4. 使用脚本将文件输出到iplist子模块并提交GitHub update分支（可在workflows修改）


## 配置文件
```json
{
    "output": {
        // 全局文件输出参数
        "directory_name": "iplist", // 项目目录
        "main_ipv4_filename": "iplist_all_ipv4", // ipv4总文件名
        "main_ipv6_filename": "iplist_all_ipv6", // ipv6总文件名
        "extension_name": "txt" // 全局输出文件后缀
    },
    "spiders": [
        // 爬虫参数 可多个爬虫
        {
           "directory_name": "Google", //文件夹名称
            "keyword": "GOOGLE LLC", //关键词 http://whois.ipip.net/search/GOOGLE%20LLC
            "ipv4": true, //抓取ipv4
            "ipv6": false, //抓取ipv6
            "main_include": true, //主文件包含
            "all_in_file": true //额外输出单文件
        },
        {
            "directory_name": "Youtube",
            "keyword": "YOUTUBE",
            "ipv4": true,
            "ipv6": false,
            "main_include": true,
            "all_in_file": true
        },
        {
            "directory_name": "Telegram",
            "keyword": "TELEGRAM",
            "ipv4": true,
            "ipv6": false,
            "main_include": true,
            "all_in_file": true
        }
    ]
}
```

## 鸣谢
- IP段由ipip.net提供