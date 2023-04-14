#
# 1.获取当前时间
```py
from datetime import datetime
def getNowTime():
    now = datetime.now()
    print(now, now.strftime('%Y%m%d%H%M%S') + '000')
    return now.strftime('%Y%m%d%H%M%S') + '000'
```

# 2.pip安装requirements.txt
```bash
pip install -r path
```