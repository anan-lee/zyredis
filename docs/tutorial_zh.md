# zyredis ʹ���ĵ�

zyredis ��һ���ṩredis ��redis proxy failover��python client�˽���������������codis ��Ϊredis proxyʱpython��client pipeline���֧�ֵ����⣬�ṩ���Ѻõ���־����codis��֧�ֵ����
zyredisͬʱҲ��һ��redis��client��zyredisͬʱ֧��ԭ��redis client�Լ�codis redis client����ģʽ�����̶�����codis��ʹ������Ǩ���ϲ��ػ�̫�ྫ����
zyredis����һ�������������һ���򻯰汾��redis orm��ʹ��zyredis���������е�redis key����ɢ�䵽��Ŀ�ĸ����ط���ʹ��zyredis���԰�������redis��key���������zyredis�ṩ�˶�redis������ص�������Ż�������
��������redis�Ĳ���zyredis���������Ż���ʹ��������������������������redis��

zyredis��Ҫ�����¼����ļ����ɣ�
* manager: ����redis�����Ӻ�����
* client���ṩredis client�Լ�codis redis client���ְ汾��֧�֣�codis�汾��Ҫ���pipeline��������쳣���⡣
* model: �ṩredis model ��odm֧��
* types���ṩ��pythonic ��ʽʹ��redis client
* serialization���ṩ�˶�redis���ݵ����л��뷴���л�����

## zyredis ��qconf��ʹ��˵��

qconf_py.so�� ���ļ���QConf��Ŀ�ṩ��python��չ������õ��������������������±����滻,�ð������ṩ��qconf�Ĳ������������Բ�ʹ��

## zyredis �����ӿڵ�ʹ�þ�����ο�testĿ¼�µĲ�����������������Ը����ӿڵ���ϸ�����Լ�˵��

## ������1.0.0�汾˵��
RedisManager.instance().init�����Ƴ���������qconf�����ж�ȡ����ֱ��ʹ�����·����滻
RedisManager.instance().init_from_qconf("/test_group/service/codis")

RedisManager�ṩ�˶�ԭ��redis��֧�֣������˶�redis���ò����Ĵ���,ֻ��Ҫ����BaseModel��ʱ�����¼����������Ǽ���
```py
class BaseRedisModel(Model):

    client_name = "test_redis"
    db_num = 0
    init_from = "local"
    redis_conf = {
        0:"redis://localhost:6389/test_redis?weight=1&transaction=1&db=0",
        1:"redis://localhost:6389/test_redis2?weight=3&transaction=1&db=0",
    }
```
����д������ʹ��ԭ��redis�����ã�redis_conf������ָ��������init_from����Ϊlocal����
