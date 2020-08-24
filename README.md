# Tutorial Flask App
## nesse tutorialzinho veremos como criar um mini projeto com crud e tals usando flask

_bora lá então!_

----

Primeiramente iremos preparar o ambiente:
```sh
apt update && apt upgrade
apt install python3 python3-pip


mkdir Batata 
cd Batata

python3 -m venv VenvBatata
. VenvBatata/bin/activate

pip install --upgrade pip
pip install flask

```

agora vamos ao código:

mas primeiro vamos criar um arquivo python
```sh
echo '' > app.py
```
OU
```sh
touch app.py
```
o importante é criar um arquivo, não importa os meuos...

após isso, em seu editor de texto preferido, abra esse arquivo app.py
que acabamos de criar

por praticidade vou abrir no vim, que é um editor de texto que roda no terminal
(eu recomendo usar ele pq é leve e muito bom)
para instalar basta usar os comandos:
```sh
apt install vim 
# se td ocorrer bem, user o seguinte comando para editar o app.py
vim app.py
# ATENÇÃO: se tiver um arquivo com o nome especificado
# ele irá abrir esse arquivo, caso contrário ele criará um

# para editar/ escrever um arquivo, digite i e aperte enter 
# isso fara com q vc entre no modo de edição
# para salvar vc aperta a tecla  ESC  e após  :wq
# isso fara com q o arquivo seja salvo, para sair sem salvar é a mesma lógica, porem :q ao invés de :wq 
```

Agora sim, vamos ao código!
```sh

from flask import Flask

app = Flask(__name__)


@app.route("/")
def index():
	return '<center><h1>Salve Rapeize! App flask na área!!</h1></center>'


if __name__ == '__main__':
	app.run()

```


Pronto! simples assim kk.
Obviamente não é um  Netflix da vida, mas já é funcional.
Bora ver essa blzinha funcionar:

rode o comando a seguir para iniciar o app:
```sh
python3 app py
```
e vc verá a seguinte saida no terminal:
```sh
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```

_não se preocupe com o WARNING nem com o código, irei explica lo Jajá_

abra seu navegador e acesse a url [127.0.0.1:5000](http://127.0.0.1:5000)
e vc verá a seguinte saída:

---
AQUI VAI FICAR UMA IMAGEM EM BREVE
---

blz, vamos explicar oq cada coisa faz..


Primeiro importamos a classe Flask do modulo flask
```sh
from flask import Flask
```
após instanciamos a class Flask em um objeto

```sh
app = Flask(__name__)
```
mas e o pq tem esse argumento name
```sh
__name__
```

a explicação é simples, ele informa ao flask o nome do app
por exemplo, se o arquivo se chamar 'Valdecir', ele ira passar esse nome ao 
app.
Você também pode passar o nome do app se preferir 
```sh
app = Flask('app')
```
mas se você mudar o nome do arquivo, terá que renomear essa parte do código, certo?


blz, após isso temos:
```sh
@app.route('/')
```

o @app.route('/') indica que toda vez q alguém acessar a rota principal
do seu app, ele ira retornar essa função que esta logo a seguir (index por exemplo)


esse @app.route() é um decorator que foi herdado da class Flask
não vamos ir a fundo nisso pois não é relevante para o tutorial,
porem é algo muito interessante de se estudar

após o decorator temos uma função, cujo nome, demos de index:
```sh
def index():
	return '<center><h1>Salve Rapeize! App flask na área!!</h1></center>'
```
 essa função está retornando um código html,as poderia ser um json,
uma string, um redirecionamento, e uma infinidade de coisas
Oque eu quero dizer: Essa função poderá receber dados, trata los, salva los,
modifica los, excluir etc e tal, e por fim deve retornar alguma coisa,
nem que seja um mizero par de aspas.

ficou um pouco extenso esse pequeno app,as eu acho isso crucial pois é essa a lógica de um App
Flask, vc importa a classe, instancia um app, cria uma rota e em seguida executa o mesmo
Espero que tenham compreendido até aqui, possam fazer esse pequeno app funcionar, e que façam testes
com a saida do app, possam fprçar erros, pq assim vcs nós aprendemos mais.

neste 'capítulo' é só isso, vamos ao próximo agora
