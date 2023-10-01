# Домашнее задание к занятию "Защита хоста" - Наталья Мартынова (Пономарева)

### Задание 1

- `Поскольку описанный в презентации алгоритм не сработал (см. далее) пришлось ипровизировать` 

`Неудачная попытка создания пользователя с зашифрованной директорией`
```
sudo adduser --encrypt-home anonimus
Unknown option: encrypt-home
```
`Классическое создание пользователя и кое-какие промежуточные действия`
```
sudo adduser anonimus
sudo apt install rsync
sudo modprobe ecryptfs
```
`Миграция домашней директории`
```
sudo ecryptfs-migrate-home -u anonimus
```
![Снимок1](https://github.com/NatoshFehn/hw-sec-02/blob/main/Снимок1.png)

`Ключ восстановления`
```
anonimus@mysql:~$  ecryptfs-unwrap-passphrase
Passphrase:
0eac72c6f4338e13196a789e45efbc66
```
![Снимок2](https://github.com/NatoshFehn/hw-sec-02/blob/main/Снимок2.png)

### Задание 2

![Снимок3](https://github.com/NatoshFehn/hw-sec-02/blob/main/Снимок3.png)

### Задание 3

![Снимок4](https://github.com/NatoshFehn/hw-sec-02/blob/main/Снимок4.png)
