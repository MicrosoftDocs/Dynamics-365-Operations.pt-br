---
title: Criar expressões de ER para chamar métodos de classe de aplicativo
description: Este artigo descreve como reutilizar a lógica de aplicativo existente em configurações de ER (relatório eletrônico) chamando métodos necessários de classes de aplicativos.
author: NickSelin
ms.date: 11/02/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0fb0a9725d882fdc330d7adbb49bd3dcadf7805f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883615"
---
# <a name="design-er-expressions-to-call-application-class-methods"></a>Criar expressões de ER para chamar métodos de classe de aplicativo

[!include [banner](../../includes/banner.md)]

Este artigo descreve como reutilizar a lógica de aplicativo existente nas configurações do [Relatório eletrônico (ER)](../general-electronic-reporting.md) chamando métodos necessários de classes de aplicativos em expressões de ER. Os valores de argumentos para classes de chamada podem ser definidos dinamicamente no runtime. Por exemplo, os valores podem ser baseados nas informações do documento de análise para garantir sua correção.

Por exemplo, neste artigo, você criará um processo que analisa extratos bancários de entrada para uma atualização de dados do aplicativo. Você receberá os extratos bancários de entrada como arquivos de texto (.txt) que contêm códigos IBAN (International Bank Account Number). Como parte do processo de importação de extratos bancários, você precisa validar a exatidão do código IBAN usando a lógica que já está disponível.

## <a name="prerequisites"></a>Pré-requisitos

Os procedimentos neste artigo destinam-se a usuários aos quais foi atribuída a função de **Administrador do sistema** ou **Desenvolvedor de relatório eletrônico**.

Os procedimentos podem ser concluídos usando qualquer conjunto de dados.

Para concluí-los, você deve baixar e salvar o seguinte arquivo: [SampleIncomingMessage.txt](https://download.microsoft.com/download/8/0/a/80adbc89-f23c-46d9-9241-e0f19125c04b/SampleIncomingMessage.txt).

Neste artigo, você criará as configurações do ER necessárias para a empresa de exemplo, Litware, Inc. Portanto, antes de concluir os procedimentos deste artigo, você deve seguir estas etapas.

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações da localização**, verifique se o provedor de configuração da empresa de exemplo **Litware, Inc.** está disponível e marcado como ativo. Se não visualizar este provedor de configuração, você deve primeiro concluir as etapas em [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-a-new-er-model-configuration"></a>Importar uma nova configuração de modelo de ER

1. Na página **Configurações de localização**, na seção **Provedores de configuração**, selecione o título para o provedor de configuração da **Microsoft**.
2. Selecione **Repositórios**.
3. Na página **Repositórios de localização**, selecione **Mostrar filtros**.
4. Para selecionar o registro de repositório Global, adicione um campo de filtro **Nome**.
5. No campo **Nome**, digite **Global**. Em seguida, selecione o operador de filtro **contém**.
6. Selecione **Aplicar**.
7. Selecione **[Abrir](../er-download-configurations-global-repo.md#open-configurations-repository)** para revisar a lista de configurações de ER no repositório selecionado.
8. Na página **Repositório de configuração**, na árvore de configuração, selecione **Modelo de pagamento**.
9. Na Guia Rápida **Versões**, se o botão **Importar** estiver disponível, selecione-o e em seguida, selecione **Sim**.

    Se o botão **Importar** não estiver disponível, você já importou a versão selecionada da configuração de ER do **Modelo de pagamento**.

10. Feche a página **Repositório de configuração** e, em seguida, feche a página **Repositórios de localização**.

## <a name="add-a-new-er-format-configuration"></a>Adicionar uma nova configuração de formato de ER

Adicionar um novo formato de ER para analisar extratos bancários de entrada no formato TXT.

1. Na página **Configurações de localização**, selecione o bloco **Configurações do relatório**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, selecione **Modelo de pagamento**.
3. Selecione **Criar configuração**. 
4. Na caixa de diálogo suspensa, siga estas etapas:

    1. No campo **Novo**, insira **Formato baseado no modelo de dados PaymentModel**.
    2. No campo **Nome**, insira **Formato de importação de extrato bancário (exemplo)**.
    3. No campo **Dá suporte à importação de dados**, selecione **Sim**.
    4. Selecione **Criar configuração** para finalizar a criação da configuração.

## <a name="design-the-er-format-configuration--format"></a>Criar a configuração de formato de ER - Formato

Cria um formato de ER que representa a estrutura prevista do arquivo externo no formato TXT.

1. Para a configuração de formato **Formato de importação de extrato bancário (exemplo)** que você adicionou, selecione **Designer**.
2. Na página **Designer de formato** na árvore de estrutura de formato no painel esquerdo, selecione **Adicionar raiz**.
3. Na caixa de diálogo que aparece, siga estas etapas:

    1. Na árvore, selecione **Sequência de\\Texto** para adicionar um componente de formato da **Sequência**.
    2. No campo **Nome**, digite **Raiz**.
    3. No campo **Caracteres especiais**, selecione **Nova linha - Windows (CR LF)**. Com base nessa configuração, cada linha no arquivo de análise será considerada como um registro separado.
    4. Selecione **OK**.

4. Selecione **Adicionar**.
5. Na caixa de diálogo que aparece, siga estas etapas:

    1. Na árvore, selecione **Texto\\Sequência**.
    2. No campo **Nome**, insira **Linhas**.
    3. No campo **Multiplicidade**, selecione **Um muitos**. Com base nessa configuração, espera-se que pelo menos uma linha seja apresentada no arquivo de análise.
    4. Selecione **OK**.

6. Na árvore, selecione **Raiz\\Linhas** e selecione **Adicionar Sequência**.
7. Na caixa de diálogo que aparece, siga estas etapas:

    1. No campo **Nome**, insira **Campos**.
    2. No campo **Multiplicidade**, selecione **Exatamente um**.
    3. Selecione **OK**.

8. Na árvore, selecione **Raiz\\Linhas\\Campos** e selecione **Adicionar**.
9. Na caixa de diálogo que aparece, siga estas etapas:

    1. Na árvore, selecione **Texto\\String**.
    2. No campo **Nome**, insira **IBAN**.
    3.. Selecione **OK**.

10. Selecione **Salvar**.

A configuração agora está definida de forma que cada linha no arquivo de análise contenha o único código IBAN.

![A configuração de formato Formato de importação de extrato bancário (exemplo) na página Designer de formato.](../media/design-expressions-app-class-er-01.png)

## <a name="design-the-er-format-configuration--mapping-to-a-data-model"></a>Criar a configuração de formato de ER – Mapeamento para um modelo de dados

Crie um mapeamento de formato ER que usa informações do arquivo de análise para preencher um modelo de dados.

1. Na página **Designer de formato**, no Painel de Ações, selecione **Mapear formato para modelo**.
2. Na página **Modelo para mapeamento de fonte de dados**, no Painel de Ações, selecione **Novo**.
3. No campo **Definição**, selecione **BankToCustomerDebitCreditNotificationInitiation**.
4. No campo **Nome**, insira **Mapeamento para modelo de dados**.
5. Selecione **Salvar**.
6. Selecione **Designer**.
7. Na página **Designer de mapeamento de modelo**, na árvore **Tipos de fontes de dados**, selecione **Dynamics 365 for Operations\\Classe**.
8. Na seção **Fontes de dados**, selecione **Adicionar raiz** para adicionar uma fonte de dados que chame a lógica de aplicativo existente para a validação de códigos IBAN.
9. Na caixa de diálogo que aparece, siga estas etapas:

    1. No campo **Nome**, digite **Check\_codes**.
    2. No campo **Classe**, digite ou selecione **ISO7064**.
    3. Selecione **OK**.

10. Na árvore **Tipos de fonte de dados**, siga estas etapas:

    1. Expanda a fonte de dados **formato**.
    2. Expanda **formato\\Raiz: Sequência(Raiz)**.
    3. Expanda **formato\\Raiz: Sequência(Raiz)\\Linhas: Sequência 1..\* (Linhas)**.
    4. Expanda **formato\\Raiz: Sequência(Raiz)\\Linhas: Sequência 1..\* (Linhas)\\Campos: Sequência 1..1 (Campos)**.

11. Na árvore **Modelo de dados**, siga estas etapas:

    1. Expanda o campo **Pagamentos** do modelo de dados.
    2. Expanda **Pagamentos\\Conta de Credor(CreditorAccount)**.
    3. Expanda **Pagamentos\\Conta do Credor(CreditorAccount)\\Identificação**.
    4. Expanda **Pagamentos\\Conta do Credor(CreditorAccount)\\Identificação\\IBAN**.

12. Siga estas etapas para vincular componentes do formato configurado aos campos do modelo de dados:

    1. Selecione **formato\\Raiz: Sequência(Raiz)\\Linhas: Sequência 1..\* (Linhas)**.
    2. Selecione **Pagamentos**.
    3. Selecione **Associar**. Com base nessa configuração, cada linha no arquivo de análise será considerada um pagamento único.
    4. Selecione **formato\\Raiz: Sequência(Raiz)\\Linhas: Sequência 1..\* (Linhas)\\Campos: Sequência 1..1 (Campos)\\IBAN: String(IBAN)**.
    5. Selecione **Pagamentos\\Conta do Credor(CreditorAccount)\\Identificação\\IBAN**.
    6. Selecione **Associar**. Com base nessa configuração, o campo **IBAN** do modelo de dados será preenchido com o valor do arquivo de análise.

    ![Associação de componentes de formato a campos de modelo de dados na página Designer de mapeamento de modelos.](../media/design-expressions-app-class-er-02.png)

13. Na guia **Validações**, siga estas etapas para adicionar uma regra de [validação](../general-electronic-reporting-formula-designer.md#Validation) que mostra uma mensagem de erro para qualquer linha no arquivo de análise que contém um código IBAN inválido:

    1. Selecione **Novo** e escolha **Editar condição**.
    2. Na página **Designer de fórmula**, na árvore **Fonte de dados**, expanda a fonte de dados **Check\_codes** que representa a classe do aplicativo **ISO7064** para exibir os métodos disponíveis dessa classe.
    3. Selecione **Check\_codes\\verifyMOD1271\_36**.
    4. Selecione **Adicionar fonte de dados**.
    5. No campo **Fórmula**, insira a seguinte [expressão](../general-electronic-reporting-formula-designer.md#Binding): **Check\_codes.verifyMOD1271\_36(format.Root.Rows.Fields.IBAN)**.
    6. Selecione **Salvar** e feche a página.
    7. Selecione **Editar mensagem**.
    8. Na página **Designer de fórmula**, no campo **Fórmula**, digite **CONCATENATE("Invalid IBAN code has been found:&nbsp;", format.Root.Rows.Fields.IBAN)**.
    9. Selecione **Salvar** e feche a página.

    Com base nessas definições, a condição de validação retornará *[FALSE](../er-formula-supported-data-types-primitive.md#boolean)* para qualquer código IBAN inválido chamando o método **verifyMOD1271\_36** existente da classe do aplicativo **ISO7064**. Observe que o valor do código IBAN é definido dinamicamente no runtime como o argumento do método de chamada baseado no conteúdo do arquivo de texto de análise.

    ![Regra de validação na página Designer de mapeamento do modelo.](../media/design-expressions-app-class-er-03.png)

14. Selecione **Salvar**.
15. Feche a página **Designer de mapeamento de modelos** e feche a página **Modelo para mapeamento de fonte de dados**.

## <a name="run-the-format-mapping"></a>Executar o mapeamento de formato

Para fins de teste, execute o mapeamento de formato usando o arquivo SampleIncomingMessage.txt, que foi baixado anteriormente. A saída gerada incluirá dados que serão importados do arquivo de texto selecionado e transferidos para o modelo de dados personalizado durante a importação real.

1. Na página **Modelo para mapeamento da fonte de dados**, selecione **Executar**.
2. Na página **Parâmetros do relatório eletrônico**, selecione **Procurar**, navegue até o arquivo **SampleIncomingMessage.txt** baixado e selecione-o.
3. Selecione **OK**.
4. Observe que a página **Modelo para mapeamento de fontes de dados** mostra uma mensagem de erro sobre um código IBAN inválido.

    ![Resultado da execução do mapeamento de formato da página Modelo para mapeamento da fonte de dados.](../media/design-expressions-app-class-er-04.png)

5. Examine a saída no formato XML, que representa os dados que foram importados do arquivo selecionado e transferidos para o modelo de dados. Observe que somente três linhas do arquivo de texto importado foram processadas sem erros. O código IBAN online 4 não é válido e foi ignorado.

    ![Saída XML.](../media/design-expressions-app-class-er-05.png)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
