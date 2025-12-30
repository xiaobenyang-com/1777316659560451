# CPAN包信息服务器 CPAN Package Info

一个MCP服务器，用于获取CPAN包的README内容、元数据和搜索功能。
An MCP server for obtaining the README content, metadata and search function of CPAN packages.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| get_readme_from_cpan | Get package README and usage examples from CPAN |
| get_package_info_from_cpan | Get package basic information and dependencies from CPAN |
| search_packages_from_cpan | Search for packages in CPAN |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659560451](https://mcp.xiaobenyang.com/inspector/1777316659560451)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659560451](https://mcp.xiaobenyang.com/inspector/1777316659560451)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "CPAN包信息服务器": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659560451/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "CPAN包信息服务器": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659560451/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "CPAN包信息服务器": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659560451",
          },
          "transport": "stdio"
        }
      }
}

```
