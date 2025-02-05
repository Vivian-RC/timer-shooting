# 🚦 Temporizador de Um Disparo (One Shot) - Raspberry Pi Pico W

Este projeto implementa um **sistema de temporização para o acionamento de LEDs** utilizando o microcontrolador **Raspberry Pi Pico W**. O sistema aciona três LEDs (**azul, vermelho e verde**) com base no clique de um **botão (pushbutton)** e realiza uma mudança sequencial dos LEDs a cada **3 segundos**. Utiliza a função `add_alarm_in_ms()` do **Pico SDK** para configurar temporizadores e funções callback.

Repositório do projeto: **[Vivian-RC/timer-shooting](https://github.com/Vivian-RC/timer-shooting.git)**

---

## 🎯 **Objetivo**

O objetivo do projeto é criar um **sistema de temporização de LEDs** em resposta ao clique de um botão, garantindo que a mudança de estado dos LEDs aconteça após um intervalo de 3 segundos. O sistema segue os seguintes requisitos:

### **Sequência de LEDs:**

1. Quando o **botão** for pressionado, **todos os LEDs (azul, vermelho e verde) serão acionados**.
2. Após **3 segundos**, o **LED azul será desligado**, mantendo o LED vermelho e verde acesos.
3. Após mais **3 segundos**, o **LED vermelho será desligado**, deixando apenas o LED verde aceso.
4. Após **3 segundos**, o **LED verde será desligado**, finalizando a sequência.

### **Comportamento do Botão:**

- O botão **só pode iniciar a sequência quando o último LED for desligado**.
- Durante a execução da sequência, **novas pressões no botão não terão efeito**.

### **Debounce (Opcional):**

- Foi implementada uma rotina **software debounce** para evitar acionamentos incorretos do botão.

---

## 🛠 **Componentes Necessários**

- **Microcontrolador:** Raspberry Pi Pico W
- **LEDs:** Azul, Vermelho e Verde
- **Resistores:** 3 resistores de **330Ω** (1 para cada LED)
- **Botão:** Pushbutton
- **Ferramenta de Simulação:** Wokwi ou BitDogLab

---

## ⚡ **Esquema de Ligação (GPIOs)**

| Componente       | GPIO |
| ---------------- | ---- |
| **LED Azul**     | 11   |
| **LED Vermelho** | 12   |
| **LED Verde**    | 13   |
| **Botão**        | 6    |

**Nota:** Para o experimento na **BitDogLab**, os LEDs estão nas portas **GPIO 11, 12 e 13**, e o botão está na **GPIO 5**.

---

## 🚀 **Como Compilar e Executar**

### **1️⃣ Clonar o repositório:**

```bash
 git clone https://github.com/Vivian-RC/timer-shooting.git
```

### **2️⃣ Entrar na pasta do projeto:**

```bash
 cd timer-shooting
```

### **3️⃣ Configurar o Ambiente de Desenvolvimento**

Certifique-se de que o **Raspberry Pi Pico SDK** e o **compilador C/C++** estão instalados.

#### **Passo 1: Instalar Ninja**

1. Baixe o **Ninja** [neste link](https://github.com/ninja-build/ninja/releases).
2. Extraia o arquivo **.zip** e coloque o **ninja.exe** em uma pasta acessível.

#### **Passo 2: Adicionar Ninja ao Path**

1. Abra **Configurações do Sistema** → **Variáveis de Ambiente**.
2. No campo `Path`, adicione o caminho da pasta onde está o `ninja.exe`.
3. No terminal, verifique se a instalação foi bem-sucedida:

```bash
 ninja --version
```

#### **Passo 3: Configurar e Compilar o Projeto**

1. Criar a pasta `build` e entrar nela:

```bash
 mkdir build && cd build
```

2. Configurar o projeto com o **CMake**:

```bash
 cmake -G Ninja ..
```

3. Compilar o projeto:

```bash
 ninja
```

4. O arquivo **main.elf** será gerado na pasta `build`.

---

## 🖥️ **Execução no Simulador Wokwi**

Se quiser testar o código no **simulador Wokwi**, use a extensão do **VSCode**:

🔗 [Extensão Wokwi para VSCode](https://marketplace.visualstudio.com/items?itemName=Wokwi.wokwi-vscode)

Se precisar de mais informações, acesse o repositório no [**GitHub**](https://github.com/Vivian-RC/timer-shooting.git) 🚀.

