# Project-POO
Sistema de gestão de dispositivos inteligentes desenvolvido no âmbito da Unidade Curricular de **Programação Orientada aos Objetos (POO)** na Universidade do Minho (2025/2026).

O **Domus Control** permite aos utilizadores gerir as suas casas inteligentes, organizando-as por divisões e associando diversos tipos de dispositivos conectados, com suporte para automações, cenários e escalonamentos temporais.

## 🚀 Funcionalidades Principais

- **Gestão de Entidades**: Criação e gestão de Utilizadores, Casas, Divisões e Dispositivos.
- **Hierarquia de Dispositivos**: Suporte para Lâmpadas, Tomadas, Cortinas, Colunas de Som, Portões de Garagem e Sensores (Luz e Água).
- **Motor de Automação**: Configuração de regras baseadas em condições (ex: detetar chuva ou baixa luminosidade) que disparam ações automáticas.
- **Cenários**: Execução de conjuntos de ações pré-definidas (ex: Modo Cinema, Sair de Casa).
- **Escalonamentos**: Agendamento de ações pontuais ou em intervalos de tempo específicos.
- **Persistência de Dados**: Salvaguarda e carregamento do estado completo da aplicação através de serialização de objetos.
- **Estatísticas**: Análise de consumo energético, dispositivos mais utilizados e divisões com maior densidade de hardware.

## 🛠️ Tecnologias Utilizadas

- **Linguagem**: Java (JDK 17 ou superior)
- **Testes Unitários**: JUnit 5
- **Gestão de Build**: Makefile
- **Documentação**: Javadoc

## 🏗️ Arquitetura do Sistema

O projeto segue o padrão **MVC (Model-View-Controller)** para garantir a separação de responsabilidades:
- **Model**: Entidades base e lógica de negócio (`Utilizador`, `Casa`, `Dispositivo`, `Automacao`).
- **View**: Interface de linha de comandos (CLI) interativa com suporte para cores ANSI e dashboards dinâmicos.
- **Controller**: Classe central `DomusControl` que atua como fachada para a gestão do estado e execução de regras.

Conceitos de POO aplicados:
- **Encapsulamento**: Atributos privados com acesso via métodos públicos e princípios de \"Most Qualified Class\".
- **Herança e Polimorfismo**: Hierarquia abstrata de dispositivos e ações.
- **Abstração**: Uso de interfaces para condições e classes abstratas para componentes base.

## 🧪 Testes e Robustez

O projeto inclui uma suite de **153 testes unitários** com 100% de sucesso, cobrindo:
- Lógica de modelos e controladores.
- Motor de automação e regras complexas.
- Validação de interface e inputs.
- **Testes de Stress**: Verificação de resiliência com 5000 utilizadores, 500 casas e 5000 dispositivos, além de testes de fuga de memória e fuzzing de strings gigantes.

## 📋 Como Executar

Certifique-se de que tem o Java instalado.

1.  **Compilar o projeto**:
    ```bash
    make compile
    ```

2.  **Executar a aplicação**:
    ```bash
    make run
    ```

3.  **Correr os testes**:
    ```bash
    make test
    ```

## 📁 Estrutura de Diretórios

```text
.
├── src/
│   ├── main/
│   │   ├── automacao/    # Lógica de regras, cenários e escalonamentos
│   │   ├── controller/   # Fachada DomusControl
│   │   ├── Exceptions/   # Exceções personalizadas
│   │   ├── model/        # Entidades do domínio
│   │   └── view/         # Interface CLI e Menu
│   └── test/             # Suite de testes JUnit 5
├── bin/                  # Ficheiros compilados
├── lib/                  # Bibliotecas externas (JUnit)
├── Makefile              # Automação de tarefas
└── README.md

👥 Autores - Grupo 8
Carlos Martins (A109507)

Diogo Vieira (A109744)

Tomás Machado (A104186)

Projeto desenvolvido para a UC de Programação Orientada aos Objetos - Universidade do Minho.
