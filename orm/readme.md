# xweb框架 ORM模块

lifei <lifei@7v1.net>

v1.0 2012-06-08

## 使用说明

### 配置文件

* 代码: settings.py

    db = {
    
        'default': {
            'host': '127.0.0.1',
            'user': 'root',
              'db': 'xweb',
         'charset': 'utf-8'
        },
        
        'userdb':  {
            'host': '127.0.0.1',
            'user': 'root',
              'db': 'userdb',
         'charset': 'utf-8'
        },
    
    }
    
    cache = {
    
        'default: {
            'host': '127.0.0.1',
            'port': 12580
        }
    }
    
* 代码：console.py
    
    from settings import db, cache
    
    config = {
        'db':db,
        'cache':cache
    }
    
    XConfig.load(config)
    
    user = User.get(1)
    user.name = 'lifei'
    
    users = User.getMulti('city_id=%s', (10010,))
    
    for user in users:
        print user.city.name
    
    UnitOfWork.inst().commit()