Elasticserach + Kibana + Filebeat
=========

Этот playbook устанавливает и настраивает Elasticserach, Kibana, Filebeat c использованием ролей описанных в файле requirements.yml


Предварительная настрока
--------------
 1. Установка ролей:  
   ```
   ansible-galaxy install -r requirements.yml --force
   ```
 2. Пример настройки хостов: /inventory  
  ```
  all:
  hosts:
    el-instance:
      ansible_host: 51.250.7.92
    kib-instance:
      ansible_host: 178.154.223.99
    fil-instance:
      ansible_host: 178.154.221.85        
  vars:
    ansible_connection: ssh
    ansible_user: opuser
elasticsearch:
  hosts:
    el-instance:
kibana:
  hosts:
    kib-instance:
filebeat:
  hosts:
    fil-instance:     
  ```
Запуск установки
--------------
```
 ansible-playbook site.yml -i inventory/prod 

```

License
-------

BSD