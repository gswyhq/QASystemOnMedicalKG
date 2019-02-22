
通过`~$ python3 build_medicalgraph.py `向neo4j导入数据太耗时；

故导入完成后，通过下方法导出neo4j 数据到文件中:
```
CALL apoc.export.cypher.all("/var/lib/neo4j/data/QASystemOnMedicalKG_all.cypher",{})
```

再通过下面方法导入文件中的数据到neo4j
```
gswyhq@gswyhq-PC:~$ docker exec -it yiyao_neo4j_7474 /bin/bash
bash-4.4# ./bin/neo4j-shell -file data/QASystemOnMedicalKG_all.cypher
```
