## UBUNTU
#### Импорт в базу
```bash
mysql -u root -p bosh.kz <  admin_bosch.sql
mysql -u admin_sony_dev -p admin_sony_dev <  admin_sonycenter.sql
```

#### Рестарт апаче
```bash
sudo /etc/init.d/apache2 restart
```

#### Даем права на авторства
```bash
sudo chown -R www-data:website /var/www/Opencart/opencart-3.0.x/
```


#### Даем доступ всем пользователям в группе
```bash
sudo chmod -R g+rwx /var/www/Opencart/opencart-3.0.x/storage/upload/
```


## GIT
#### На стороне сервера жестка принимаем последние коммиты
```git
git fetch origin
git reset --hard origin/master
```

#### Simple Way to remove untracked files
```
git add --all
git reset --hard HEAD
```

#### Отменить последний коммит, но оставить все изменения коммита
```
git reset --soft HEAD~1
```

#### Архивировать только изменения между ветками
```
git diff --name-only master |  xargs git archive -o output.zip HEAD --
```

#### Несмотрим на изменения в файлмоде
```
git config --unset core.filemode
```

#### Если .gitignore не работает удалить из кэша
```
git rm -rf --cached .
git add .
git commit -m "fix gitignore"
```

#### Сравнения двух файлов
```
git diff [--options] <commit> <commit> [--] [<path>...]
```

#### Клонируем репозиторий как submodule
```
git clone --recurse-submodules -j8 git@bitbucket.org:ipol-core/core.git vendor/ipol/Core
```

## WGET
#### Копируем файлы с SSL сертификатом
```
wget -k -l 10 -p -E -nc https://www.lg.com/uk/tvs/lg-oled77zx9la --no-check-certificate
```
