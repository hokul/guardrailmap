# guardrailmap

**比较两套护栏规则的覆盖差异。**

`guardrailmap` —— 对齐两版护栏规则，标出新增、删除与改动的条目

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`guardrailmap.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install hokul-guardrailmap
```

装完直接用命令名调用：

```bash
guardrailmap --help
```

也可以不用安装，直接把 `guardrailmap.py` 拷走用——它只依赖标准库。

## 为什么需要它

差分要指出方向——新增了防护还是拆掉了防护

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 护栏覆盖差分 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python guardrailmap.py --file input.txt
python guardrailmap.py --text "示例内容"
python guardrailmap.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 覆盖率的分母取自你登记的清单，清单不全就会偏高。
- 只做映射，不追责。

## 跑测试

```bash
python test_guardrailmap.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/hokul/guardrailmap>

---

## 关于作者

hokul 做护栏覆盖差分相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://hokul.github.io>
- 仓库：<https://github.com/hokul/guardrailmap>

## 许可

MIT，见 [LICENSE](LICENSE)。
