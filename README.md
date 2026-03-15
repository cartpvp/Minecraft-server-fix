# Minecraft-server-fix
Если вы живете в РФ у вас 30 секундное подключение к миру а потом Timed out при подключении к западному серверу майнкрафт то этот гайд для вас

## ФИКС:
1. Открываете командную строку - ``Win + R -> cmd`` и вставляете эту строку: ``nslookup -type=SRV _minecraft._tcp.айпи-сервера-без-порта``

2. Находите строку **port** и копируете порт.

3. Далее вам понадобится zapret, вы можете скачать его [здесь](https://github.com/flowseal/zapret-discord-youtube/releases). В нем вы находите удобный рабочий для вас **ALT файл.** Откройте его через любой текстовый редактор, хоть через блокнот.

4. В этом файле будет строка ``start "zapret: %~n0" /min "%BIN%winws.exe" --wf-tcp=80,443,2053,2083,2087,2096,8443,%GameFilter% --wf-udp=443,19294-19344,50000-50100,%GameFilter% ^``
В ``--wf.tcp=`` (ИМЕННО В TCP, не в UDP) вставьте скопированный порт или порты через запятую. Крайне рекомендую добавить порт 25565 чтобы заработало большинство серверов.

5. Под строкой из **4 пункта** вам нужно скопировать и вставить это:
``--filter-tcp=здесь-ваши-порты --ipset-exclude="%LISTS%ipset-exclude.txt" --dpi-desync-any-protocol=1 --dpi-desync-cutoff=n5 --dpi-desync=multisplit --dpi-desync-split-seqovl=582 --dpi-desync-split-pos=1 --dpi-desync-split-seqovl-pattern="%BIN%tls_clienthello_4pda_to.bin" --new ^``
В ``--filter-tcp=`` вы также вписываете ваш порт или порты через запятую из пункта 4.

6. Сохраняете файл и запускаете ALT.
