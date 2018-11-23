- Tools → New Plugin...

- 输入以下代码
```python
import datetime
import sublime_plugin
class AddCurrentTimeCommand(sublime_plugin.TextCommand):
    def run(self, edit):
        self.view.run_command("insert_snippet",
            {
                "contents": "%s" % datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
            }
        )
```

- 创建快捷键
  * Preference → Key Bindings - User
  ```
  { "keys": ["ctrl+shift+,"], "command": "add_current_time" }
  ```
