# Обновление AIProxy: навыки, инструменты, точный поиск

## Куда что копировать
- `AIProxy\*.cs` -> в проект AIProxy (Program.cs ЗАМЕНИТЬ, вернув в нём свой отпечаток сертификата; Eva.cs заменить; остальные — новые файлы).
- `Indexer\*` -> в проект индексатора (Program.cs заменить; Chunker.cs и Knowledge.cs — новые).
- `Skills\*.md` -> `O:\AI\Skills\`
- `Tools\*` -> `O:\AI\Tools\` (файл `example-tool.json.disabled` — образец внешнего инструмента: переименовать в .json).
- `appsettings.json` — положить рядом с AIProxy.exe, заполнить Eva/Gitlab при необходимости.

## Порядок
1. `nssm-llama.cmd` (от администратора) — новые параметры llama-server.
2. Собрать и опубликовать Indexer, выполнить `Indexer index --full` (формат индекса изменился).
3. Собрать и опубликовать AIProxy, перезапустить службу.
4. Проверить в чате: `/skills`, `/check ps1 Get-Process | Where {`, `/wiki <вопрос по документации>`.

## Команды чата
/skills, /skill on|off <id|группа|all>, /skill show <id>, /use id1,id2 вопрос
/check [язык] [код], /fix [язык] [код], /export docx|xlsx|html|md|txt|csv, /tools, /tool <имя> <текст>
/wiki вопрос, /normal вопрос, /eva вопрос, /report ПРОЕКТ, /task КОД, /evasync, /evatest
