## 背景

[issue#1373](https://github.com/opentofu/opentofu/issues/1373)

在`tofu init`等命令中，并不支持添加`-json`来使得输出的信息或diagnostic以JSON的格式进行输出，导致在一些CI/CD流程中，无法通过脚本和程序对命令输出进行优雅的解析来定制化返回信息的格式。

## 结论

1. `tofu init`需要支持-json
2. `tofu init -json`的输出应全为json格式

## 现状

如下图所示，在init command中，错误信息通过 Ui 上的 Error 或 Output 方法进行输出
![code1](/assest/add-json-flag-to-tofu-init/code1.png)

而 diagnostic 通过 meta 上定义的 showDiagnostics 方法输出
![code2](/assest/add-json-flag-to-tofu-init/code2.png)