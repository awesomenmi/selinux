# Selinux
## 1. Запуск nginx на нестандартному порту 3-мя разными способами:

   Проверим, запущен ли selinux:
 
   ![alt-текст](https://raw.githubusercontent.com/awesomenmi/selinux/master/screenshots/Screenshot%20from%202020-05-30%2014-13-45.png)
  
   Сменим порт на нестандратный:
  
   ![alt-текст](https://raw.githubusercontent.com/awesomenmi/selinux/master/screenshots/Screenshot%20from%202020-05-30%2014-15-06.png)
  
   Перезапустим nginx, убедимся, что служба не работает:
  
   ![alt-текст](https://raw.githubusercontent.com/awesomenmi/selinux/master/screenshots/Screenshot%20from%202020-05-30%2014-16-02.png)
  
  - **1 способ - добавим нестандартный порт (8880) в имеющийся тип:**

    ![alt-текст](https://raw.githubusercontent.com/awesomenmi/selinux/master/screenshots/Screenshot%20from%202020-05-30%2014-36-08.png)
  
  - **2 способ - cформируем и установим модуль SELinux:**
 
    Проверим, какие порты разрешены в http_port_t и учтановим утилиту setroubleshoot-server:
    
    ![alt-текст](https://raw.githubusercontent.com/awesomenmi/selinux/master/screenshots/Screenshot%20from%202020-05-30%2014-48-13.png)
   
    Проанализируем данные лога командой `sealert -a /var/log/audit/audit.log`:
    
    ![alt-текст](https://github.com/awesomenmi/selinux/blob/master/screenshots/Screenshot%20from%202020-05-30%2014-51-19.png)
    
    Скомпилируем и загрузим модуль:
    
    ![alt-текст](https://raw.githubusercontent.com/awesomenmi/selinux/master/screenshots/Screenshot%20from%202020-05-30%2014-55-03.png)
    
    Проверим, загружен ли модуль и, заодно, статус nginx:
    
    ![alt-текст](https://raw.githubusercontent.com/awesomenmi/selinux/master/screenshots/Screenshot%20from%202020-05-30%2014-56-24.png)
    
  - **3 способ - с помощью переключателей setsebool**
    
  
