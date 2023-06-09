# Домашнее задание к занятию 10.3 «Pacemaker» - `Акиньшин С.Г.`


## Задание 1

Кластер Pacemaker - это группа из нескольких узлов Pacemaker, которые работают вместе для обеспечения высокой доступности и отказоустойчивости в системах компьютерной обработки данных. Основная функция кластера Pacemaker - обеспечение непрерывной работы приложений и сервисов, даже в случае сбоев в работе отдельных узлов. Для этого кластер Pacemaker может автоматически перенаправлять запросы к работающим узлам в случае отказа какого-либо из них, а также производить автоматическое восстановление работоспособности узлов после их восстановления. Кластер Pacemaker широко применяется в высоконагруженных системах, таких как серверные фермы, базы данных, кластеры виртуальных машин и т.д.

## Задание 2

Corosync - это открытое программное обеспечение, предназначенное для создания и управления кластерами компьютеров. Основная функция Corosync - обеспечение обмена сообщениями и координации действий между узлами кластера.

С помощью Corosync узлы кластера могут обмениваться информацией о своем состоянии, а также обнаруживать отказы и изменения в кластере. Эта информация используется для принятия решений о перераспределении задач между узлами и восстановления работоспособности кластера в случае отказов.

Кроме того, Corosync обеспечивает синхронизацию данных между узлами кластера, что позволяет узлам иметь доступ к одним и тем же данным в режиме реального времени. Это особенно важно для кластеров баз данных и файловых систем, где доступ к общим данным является критически важным.

В целом, Corosync является важным компонентом для создания и управления высоконадежными кластерами компьютеров, которые используются в различных областях, включая серверное и сетевое оборудование, облачные вычисления и телекоммуникационные системы.

## Задание 3

### Конфиг: /etc/corosync/corosync.conf

```sh
totem {
    version: 2
    cluster_name: newCluster
    transport: knet
    crypto_cipher: aes256
    crypto_hash: sha256
}

nodelist {
    node {
        ring0_addr: node1
        name: node1
        nodeid: 1
    }

    node {
        ring0_addr: node2
        name: node2
        nodeid: 2
    }
}

quorum {
    provider: corosync_votequorum
    two_node: 1
}

logging {
    to_logfile: yes
    logfile: /var/log/corosync/corosync.log
    to_syslog: yes
    timestamp: on
}
```

1. `Pacemaker, Corosync, Pcs`

![JPG](https://github.com/akinya1974/Pacemaker/blob/main/JPG/1.jpg)

...

![JPG](https://github.com/akinya1974/Pacemaker/blob/main/JPG/2.jpg)

...

![JPG](https://github.com/akinya1974/Pacemaker/blob/main/JPG/3.jpg)

...


## Задание 4

С подключением сервиса DRBD пока не разобрался, но нашел установку IP адреса, для нод!)

![JPG](https://github.com/akinya1974/Pacemaker/blob/main/JPG/Задание-4.jpg)

