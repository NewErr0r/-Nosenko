1. Выполните проверку связность всех серверов:
        ansible -m ping all

2. Запустите playbook:
        ansible-playbook Project_Deployer.yaml


Данный Playbook выполняет задачи ( НА ВСЕХ 3-х СЕРВЕРАХ ОДНОВРЕМЕННО описанных в файле hosts) такие как:
        -Обновление списка пакетов и установку "curl";
        -Активация межсетевого экрана "UFW";
        -Разрешение портов TCP 80,8080,1834;
        -Создание пользователя "User";
        -Установка пакета "Docker";
        -Запуск скрипта для установки "Docker-compose";
        -Создание дирректории "/skillcloud-nginx", с последующим копированием необходимых файлов для сборки образов,>
        -Перезапуск SSH и UFW;
        -Перезагрузка виртуальных машин (требуется время для перезагрузки серверов, нужно подождать Playbook отработает как надо!).
