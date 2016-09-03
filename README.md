# oracleCourse
some instructions of oracle course

SELECT * FROM dual;
SELECT 1 FROM dual;
SELECT * FROM TCLIENTES;
SELECT id, nome, dt_nascimento FROM TCLIENTES;
SELECT cod_curso, preco, preco+300, preco*0.10 FROM TCURSOS;
SELECT id, tclientes_id, desconto, total FROM TCONTRATOS;
SELECT id, tclientes_id, desconto, total, total+desconto FROM TCONTRATOS;
SELECT id, tclientes_id, NVL(desconto,0), total, total+NVL(desconto,0) FROM TCONTRATOS;
SELECT id codigo, nome AS cliente FROM tclientes;
SELECT nome "Cliente Preferencial" FROM TCLIENTES;
SELECT id||nome "Clientes" FROM TCLIENTES;
SELECT id||' - '|| nome "Clientes" FROM TCLIENTES;
SELECT nome|| ' nasceu em ' ||  dt_nascimento AS "Nascimento do Cliente" FROM TCLIENTES;
SELECT 'O telefone de '|| nome || ' é ' || telefone CLIENTE FROM TCLIENTES;
SELECT q'<Oracle's quote operator>' FROM dual;
SELECT q'<Oracle's quote operator>' AS ASPAS FROM dual;
SELECT cidade CIDADES FROM TCLIENTES;
SELECT DISTINCT cidade CIDADES FROM TCLIENTES;
SELECT DISTINCT nome CLIENTE, cidade CIDADES FROM TCLIENTES;
SELECT id, nome, dt_nascimento FROM TCLIENTES WHERE estado = 'RS';
SELECT nome, preco FROM tcursos WHERE preco BETWEEN 800 AND 1000;
SELECT nome, dt_nascimento, cidade, estado FROM TCLIENTES WHERE estado IN ('RS','RJ','PR');
SELECT nome FROM TCLIENTES WHERE nome LIKE 'A%';
SELECT nome FROM TCLIENTES WHERE (nome LIKE 'A%') OR (nome LIKE '%A%') OR (nome LIKE '_a%');
SELECT nome, dt_nascimento, cidade, estado
FROM TCLIENTES WHERE estado = UPPER('sp');
SELECT LOWER('Introdução ao ORACLE 1G') FROM DUAL;
SELECT INITCAP('Introdução ao ORACLE 1G') FROM DUAL;
SELECT CONCAT('Introdução ao ORACLE 1G', ' CURSO 1') FROM DUAL;
SELECT SUBSTR('Introdução ao ORACLE 1G',1,11) FROM DUAL;
SELECT LENGTH('Introdução ao ORACLE 1G') FROM DUAL;
SELECT REPLACE('Introdução ao ORACLE 11G','11G', '12G') FROM DUAL;
SELECT INSTR('Introdução ao ORACLE 1G', 'ORACLE') FROM DUAL;
SELECT DECODE(1,1,'SIM',2,'NAO','TALVEZ') FROM DUAL;
SELECT id, dt_compra, total, desconto
FROM TCONTRATOS
WHERE total >= 1000 AND desconto IS NOT NULL;
SELECT id, dt_compra, total
FROM TCONTRATOS
WHERE total >= 1000 OR desconto IS NOT NULL;
SELECT nome, dt_nascimento, cidade
FROM TCLIENTES
WHERE cidade NOT IN ('SAO PAULO','RIO DE JANEIRO');
SELECT ROUND(dbms_random.value(1,100)) FROM dual;
SELECT SYSDATE FROM DUAL;
SELECT nome, ROUND(((SYSDATE - dt_nascimento)/7),2) semanas
FROM TCLIENTES WHERE estado = 'SP';



