### Roteiro: Criando um Hello World com React Native e Expo no GitHub Codespaces com Tunnel e Template Blank

#### Pré-requisitos:
- Conta no GitHub com acesso ao Codespaces.
- Ambiente Codespaces configurado.
- Node.js configurado (geralmente já disponível no Codespaces).
- Expo CLI (será usado via `npx`, então não precisa ser instalado manualmente).
- Um dispositivo físico com o aplicativo **Expo Go** instalado para testar o app.

### Passo a Passo:

#### 1. **Criar ou Acessar um Repositório no GitHub:**
   - Crie um novo repositório no GitHub ou acesse um repositório existente onde você deseja desenvolver o projeto React Native.
   - Se você ainda não tiver um repositório, crie um rapidamente acessando [github.com](https://github.com), clicando em **New Repository** e preenchendo as informações necessárias.

#### 2. **Iniciar um Codespace:**
   - Acesse o repositório no GitHub.
   - No menu do repositório, clique em **Code** e depois selecione a aba **Codespaces**.
   - Clique em **New Codespace** para iniciar um novo ambiente de desenvolvimento.
   - Aguarde enquanto o Codespaces configura o ambiente (pode levar alguns minutos).

#### 3. **Verificar o Node.js:**
   - No terminal do Codespaces, verifique se o Node.js está instalado:
     ```bash
     node -v
     ```
   - Isso deve retornar a versão do Node.js. Se não estiver instalado, o Codespaces pode solicitar a instalação ou você pode seguir as instruções para configurar o Node.js.

#### 4. **Criar o Projeto Expo Usando o Template `blank`:**
   - No terminal do Codespaces, execute o comando abaixo para criar um novo projeto React Native com Expo usando o template em branco (`blank`), diretamente na pasta raiz do projeto:
     ```bash
     npx create-expo-app . --template blank
     ```
   - Isso criará o projeto Expo básico na pasta raiz do repositório atual, sem a necessidade de um template avançado, mantendo o projeto minimalista.

#### 5. **Configurar o Túnel para Conexão Expo Go:**
   - Como o Codespaces está rodando em um servidor remoto, é importante usar a opção `--tunnel` para garantir que o Expo consiga se comunicar com o seu dispositivo físico. Isso evita problemas de conexão de rede.
   - Para iniciar o servidor de desenvolvimento com túnel, execute o seguinte comando no terminal do Codespaces:
     ```bash
     npx expo start --tunnel
     ```
   - Isso abrirá uma interface web do Expo e exibirá um QR Code. O túnel garante que o seu dispositivo físico, usando o Expo Go, possa se conectar ao servidor remoto.

#### 6. **Modifique o Arquivo `App.js` para Exibir "Hello World":**
   - Abra o arquivo `App.js` na pasta raiz do projeto (você verá o arquivo no painel lateral).
   - Substitua o conteúdo do `App.js` pelo código abaixo para exibir uma simples mensagem "Hello, World!":
     ```javascript
     import { StatusBar } from 'expo-status-bar';
     import { StyleSheet, Text, View } from 'react-native';

     export default function App() {
       return (
         <View style={styles.container}>
           <Text>Hello, World!</Text>
           <StatusBar style="auto" />
         </View>
       );
     }

     const styles = StyleSheet.create({
       container: {
         flex: 1,
         backgroundColor: '#fff',
         alignItems: 'center',
         justifyContent: 'center',
       },
     });
     ```

#### 7. **Testar no Dispositivo Físico (Expo Go):**
   - Abra o aplicativo **Expo Go** no seu dispositivo Android ou iOS.
   - Use o leitor de QR Code embutido no Expo Go para escanear o QR Code gerado na interface web do Expo no navegador.
   - O aplicativo será carregado no seu dispositivo, e você verá a mensagem "Hello, World!" na tela.

#### 8. **Testar no Navegador (Opcional):**
   - Se você quiser testar o app diretamente no navegador, pode rodar a versão web do Expo:
     ```bash
     npx expo start --web
     ```
   - Isso abrirá o aplicativo no navegador, permitindo que você visualize o "Hello, World!" sem precisar de um dispositivo físico.

#### 9. **Comitar as Alterações (Opcional):**
   - Depois de testar e confirmar que o app está funcionando, você pode comitar as alterações no repositório do GitHub:
     ```bash
     git add .
     git commit -m "Add Hello World project with React Native and Expo"
     git push origin main
     ```

### Resumo:

- Criamos um projeto React Native com Expo usando o template `blank` diretamente na pasta raiz do repositório.
- Configuramos o Expo para usar o túnel com o comando `npx expo start --tunnel`, garantindo que o dispositivo físico possa se conectar ao Codespaces.
- Modificamos o arquivo `App.js` para exibir a mensagem "Hello, World!".
- Testamos o app no dispositivo físico com Expo Go e, opcionalmente, no navegador com a versão web do Expo.

Dessa forma, você tem um projeto React Native básico funcionando no ambiente remoto do Codespaces com a possibilidade de rodar em dispositivos físicos sem problemas de conexão.