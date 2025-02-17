### Порядок установки сервера
1. В файле `.env` указать домены на которых будет работать ВКС сервер. WHIP пока не обязателен и его можно пропустить.
2. Запустить `./install_server.sh` (возможно, на последнюю операцию в файле нужно sudo). Перед запуском убедиться, что в директории, 
где запускается скрипт, есть файл `.env`. Сервер будет установлен в текущей директории.
3. Если на сервере отсутствует docker, то выполнить скрипт под sudo `./install_docker.sh` (только для Ubuntu) или иным способом установить docker + compose
4. Сервер должен выходить в Интернет с выделенного IP адреса. (NAT использовать не рекомендуется)

### Проверка открытия портов
Разрешите на вашем firewall доступ к ВКС-серверу по портам:
* 443/tcp
* 8080/tcp
* 7880/tcp, 7881/tcp, 7882/udp
* 5349/tcp, 3478/udp
* Важно, сервис самостоятельно получит сертификаты с LetsEncrypt. Запускайте когда вы делегировали основной и вспомогательные домены и открыли 443/tcp порт на firewall.
