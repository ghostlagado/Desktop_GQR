# Desktop GQR — Gerador de QR Codes

Aplicação desktop em Python para consultar dados de CRs no banco de dados do Grupo GPS e gerar QR Codes prontos para impressão. Os arquivos são organizados em pastas e podem ser exportados individualmente em PNG ou reunidos em PDF.

> **Acesso à base de dados:** o aplicativo depende da conexão com a infraestrutura de banco de dados. Conecte-se à VPN corporativa (OpenVPN) e utilize credenciais autorizadas antes de iniciar.

## Tecnologias

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PyQt5](https://img.shields.io/badge/PyQt5-41CD52?style=for-the-badge&logo=qt&logoColor=white)
![SQL Server](https://img.shields.io/badge/Microsoft_SQL_Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)

Principais bibliotecas: PyQt5, SQLAlchemy, pyodbc, Pillow, NumPy, pandas, ReportLab e Segno.

## Funcionalidades

- Autenticação e conexão com o banco de dados.
- Consulta e seleção de CRs disponíveis.
- Seleção de nível, empresa e tipo de geração.
- Aplicação automática de modelos visuais conforme o CR.
- Geração de QR Codes e organização dos arquivos em diretórios.
- Exportação para imagens PNG e documentos PDF prontos para impressão.
- Abertura da pasta de saída diretamente pelo aplicativo.
- Interface desktop com tema escuro e indicador de progresso.

## Downloads

| Plataforma | Disponibilidade |
| --- | --- |
| Windows | [Baixar versão disponibilizada](https://mega.nz/file/fNUHkaxJ#cy2ckf4MBlCVDekHjDy_-P0dmlLUj8t8u-CvHYONtXI) |
| Código-fonte | [Consultar no GitHub](https://github.com/foxtec198/Desktop_GQR) |
| Linux | Não há versão publicada neste momento |
| Android | Prévia conceitual; não é uma versão funcional equivalente confirmada |

O link para Windows é hospedado externamente. Confira a origem do arquivo antes de executá-lo.

## Executar pelo código-fonte

### Requisitos

- Python compatível com as dependências listadas em `requirements.txt`.
- Driver ODBC do SQL Server instalado e configurado no ambiente.
- Acesso à rede corporativa por meio da OpenVPN, quando exigido.
- Credenciais autorizadas para o banco de dados.
- Estrutura de arquivos do projeto preservada, incluindo os recursos utilizados pela interface em `src/`.

### Instalação

1. Clone o repositório:

   ```bash
   git clone https://github.com/foxtec198/Desktop_GQR.git
   cd Desktop_GQR
   ```

2. Crie e ative um ambiente virtual:

   **Windows (PowerShell):**
   ```powershell
   python -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```

   **Linux:**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. Instale as dependências:

   ```bash
   python -m pip install --upgrade pip
   pip install -r requirements.txt
   ```

4. Com a VPN conectada e os requisitos de banco configurados, inicie a aplicação:

   ```bash
   python main.py
   ```

> **Observação:** a instalação das bibliotecas, por si só, não configura o driver ODBC, a conectividade com o SQL Server nem as permissões de acesso. Esses requisitos precisam estar disponíveis no ambiente.

## Como utilizar

### 1. Conectar ao banco de dados

![Tela de login](readme/login.PNG)

Informe o servidor e as credenciais autorizadas. Se a infraestrutura exigir, conecte-se à OpenVPN antes de tentar entrar.

### 2. Selecionar os dados

![Tela principal](readme/main.PNG)

Após o login, selecione o CR e as opções disponíveis na interface, como nível, empresa e tipo de geração. Preencha apenas os campos necessários conforme a regra de negócio.

### 3. Gerar os QR Codes

![Geração dos QR Codes](readme/gerando.PNG)

Acione a opção de gerar e aguarde o processamento. O aplicativo apresenta o resultado da operação.

### 4. Abrir os arquivos

![Resultado da geração](readme/feito.PNG)

Use **Abrir pasta** para acessar os arquivos gerados.

![Pasta de saída](readme/explorer.PNG)

A saída pode conter QR Codes individuais em PNG e documentos PDF para impressão.

![Arquivos gerados](readme/explorerAberto.PNG)

Abra o arquivo desejado para conferir o resultado antes de imprimir ou encaminhar para uma gráfica.

![Impressão](readme/imprimir.PNG)

## Solução de problemas

| Problema | O que verificar |
| --- | --- |
| Falha na conexão | VPN ativa, endereço do servidor, disponibilidade do SQL Server e credenciais autorizadas. |
| Erro relacionado a ODBC | Instalação do driver ODBC do SQL Server e compatibilidade com a arquitetura do Python/aplicativo. |
| Interface ou recursos não encontrados | Execute o projeto a partir da pasta raiz e confira se a estrutura `src/` está completa. |
| Nenhum QR Code gerado | Confira os dados selecionados, a resposta apresentada pelo aplicativo e as permissões de gravação na pasta de saída. |
| Pasta de saída não abre | Verifique se a pasta `QRCodes` foi criada e se o Windows Explorer está disponível. |

## Documentação e suporte

- [Repositório do projeto](https://github.com/foxtec198/Desktop_GQR)
- [Documentação do Desktop GQR](https://desktop-gqr.readthedocs.io/en/latest/#como-gerar)
- [Canal relacionado no YouTube](https://www.youtube.com/watch?v=W6hMMplTn0Q&t=15s)

## Segurança

- Não compartilhe credenciais do banco de dados nem as inclua em commits.
- Utilize somente servidores e contas autorizados.
- Avalie cuidadosamente os arquivos gerados antes de publicá-los: os QR Codes e PDFs podem conter informações operacionais.
- A opção de salvar credenciais deve ser usada apenas em equipamentos confiáveis e conforme as políticas da organização.

---

Desenvolvido por **tecnobreve**.