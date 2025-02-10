##  Sobre o projeto
- API em Python desenvolvida com FastAPI.
- Autômatos do tipo DPDA e DTM não possuem integração com o frontend, portanto, devem ser testados requisitando diretamente o backend, utilizando tecnologias como Postman, Insomnia ou APIdog.

##  Como rodar (em Linux)
1. É necessário possuir o `graphviz` instalado, portanto, execute no terminal:
    ```bash
    sudo apt update
    sudo apt install graphviz graphviz-dev
2. Clone o repositório:
    ```bash
    git clone https://github.com/BernardoPavani/API_MT.git
3. Crie um ambiente virtual:
   ```bash
   python -m venv venv
   source venv\bin\activate
4. Instale as dependências:
    ```bash
    pip install -r requirements.txt
5. Execute a API
    ```bash
    uvicorn main:app --reload
6. A API é executada em `localhost:8000`. Em `localhost:8000/docs`, encontra-se a documentação dos endpoints.

##  Exemplo de automatos para teste na interface

### DFA - Número impar de 0s
    {
      "type": "DFA",
      "config": {
        "states": ["q0", "q1"],
        "input_symbols": ["0", "1"],
        "transitions": {
          "q0": {"0": "q1", "1": "q0"},
          "q1": {"0": "q0", "1": "q1"}
        },
        "initial_state": "q0",
        "final_states": ["q1"]
      }
    }

### NFA - Termina em 01
    {
        "type": "NFA",
        "config": {
            "states": ["q0", "q1", "q2"],
            "input_symbols": ["0", "1"],
            "transitions": {
            "q0": {"0": ["q0", "q1"], "1": ["q0"]},
            "q1": {"1": ["q2"]},
            "q2": {}
            },
            "initial_state": "q0",
            "final_states": ["q2"]
        }
    }



