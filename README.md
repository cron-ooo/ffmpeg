# python-ffmpeg
FFmpeg Docker image

Собранные Docker-образы можно найти https://hub.docker.com/r/wladimi/dz-web-base

За базовый образ был взят python:3.9.5-slim-buster, это официальный python образ, ставить самостоятельно в дебиан эту версию излишний труд. Образ с основанный на Debian был взят специально, так как виртуалка с видеокартой для которой готовится этот базовый образ с Debian 10 обновлённый до backports, тут в образе мы тоже ставим пакеты с backports, это необходимо чтобы добиться совместимости библиотек и api cuda. Если я верно понял, то в Docker образе библиотеки должны быть или такие же как на хосте или же по крайней мере не свежее, если они свежее, то происходит конфликт api cuda. Идеально если они совпадают по версиям, к этому и стоит стремиться.
Исходя из того что описано вышу нужно быть аккуратным и следить что после пересборки базового образа у нас версии api cuda совпадают на хосте и в образе, так как в образ прилетит последнее доступное в репозиториях, а значит если не обновить хост, то работа cuda сломается.
