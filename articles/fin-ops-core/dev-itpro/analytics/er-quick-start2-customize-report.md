---
title: Ajustar um formato de ER para gerar um documento eletrônico personalizado
description: Este tópico explica como ajustar um formato de relatório eletrônico (ER) fornecido pela Microsoft para gerar um documento eletrônico personalizado.
author: NickSelin
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom:
- "220314"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ec7f5bcf9f01512d22f502a4b512f2919b3caf348eb1f5c4365238d6fd3f476
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770011"
---
# <a name="adjust-an-er-format-to-generate-a-custom-electronic-document"></a>Ajustar um formato de ER para gerar um documento eletrônico personalizado

[!include[banner](../includes/banner.md)]

Os procedimentos descritos neste tópico explicam como um usuário que tem a função de Administrador do Sistema ou de Consultor Funcional de Relatório Eletrônico pode executar estas tarefas:

- Configurar parâmetros para a [estrutura de relatórios eletrônicos (ER)](general-electronic-reporting.md).
- Importar as configurações de ER fornecidas pela Microsoft e utilizadas para gerar um arquivo de pagamento enquanto um [pagamento de fornecedor](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md) está sendo processado.
- Criar uma versão personalizada de uma configuração do formato de ER padrão fornecida pela Microsoft.
- Modificar a configuração do formato de ER personalizado para gerar arquivos de pagamento que atendam aos requisitos de um determinado banco.
- Adotar as alterações feitas na configuração do formato de ER padrão na configuração do formato de ER personalizado.

Todos os procedimentos a seguir podem ser feitos na empresa **GBSI**. Nenhum código é necessário.

- [Configurar a estrutura de ER](#ConfigureFramework)

    - [Configurar parâmetros de ER](#ConfigureParameters)
    - [Ativar um provedor de configuração de ER](#ActivateProvider)

        - [Examinar a lista de provedores de configuração de ER](#ReviewProvidersList)
        - [Adicionar um novo provedor de configuração de ER](#ActivateProvider)
        - [Ativar um provedor de configuração de ER](#ActivateAddedProvider)

- [Importar as configurações do formato de ER padrão](#ImportERSolution1)

    - [Importar as configurações de ER padrão](#ImportERFormat1)
    - [Examinar as configurações de ER importadas](#ReviewImportedERSolution)

- [Preparar um pagamento de fornecedor para processamento](#PrepareVendorPayment)

    - [Adicionar informações bancárias de uma conta de fornecedor](#AddBankAccount)
    - [Inserir um pagamento de fornecedor](#EnterVendorPayment)

- [Processar um pagamento de fornecedor usando o formato de ER padrão](#ProcessVendorPayment1)

    - [Configurar o método de pagamento eletrônico](#ConfigureMethodOfPayment1)
    - [Processar um pagamento de fornecedor](#ProcessPayment1)

- [Personalizar o formato de ER padrão](#CustomizeProvidedFormat)

    - [Criar uma formato personalizado](#DeriveProvidedFormat)
    - [Editar uma formato personalizado](#ConfigureDerivedFormat)
    - [Marcar um formato personalizado como executável](#MarkFormatRunnable)

- [Processar um pagamento de fornecedor usando o formato de ER personalizado](#ProcessVendorPayment2)

    - [Configurar o método de pagamento eletrônico](#ConfigureMethodOfPayment2)
    - [Processar um pagamento de fornecedor](#ProcessPayment2)

- [Importar novas versões das configurações do formato de ER padrão](#ImportERSolution2)

    - [Importar novas versões das configurações de ER padrão](#ImportERFormat2)
    - [Examinar as configurações do formato de ER importado](#ReviewImportedERFormat)

- [Adotar as alterações na nova versão de um formato importado em um formato personalizado](#AdoptNewBaseVersion)

    - [Concluir a versão de rascunho atual de um formato personalizado](#CompleteDerivedFormat)
    - [Trocar base de um formato personalizado para uma nova versão base](#RebaseDerivedFormat)
    - [Processar um pagamento de fornecedor usando o formato de ER com troca de base](#ProcessPayment3)

- [Recursos adicionais](#References)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a>Configurar a estrutura de ER

Como usuário na função de Consultor Funcional de Relatório Eletrônico, você deve configurar o conjunto mínimo de parâmetros de ER antes de começar a usar a estrutura de ER para criar uma versão personalizada de um formato de ER padrão.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>Configurar parâmetros de ER

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Parâmetros de relatório eletrônico**.
3. Na página **Parâmetros de relatório eletrônico**, na guia **Geral**, defina a opção **Habilitar modo de design** como **Sim**.
4. Na guia **Anexos**, defina os seguintes parâmetros:

    - No campo **Configurações**, selecione o tipo **Arquivo** para a empresa **USMF**.
    - Nos campos **Arquivo de trabalho**, **Temporário**, **Linha de base** e **Outros**, selecione o tipo **Arquivo**.

Para obter mais informações sobre parâmetros de ER, consulte [Configurar a estrutura de ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>Ativar um provedor de configuração de ER

Toda configuração de ER adicionada é marcada como pertencente a um provedor de configuração de ER. O provedor de configuração de ER ativado no espaço de trabalho **Relatório eletrônico** é usado para essa finalidade. Por isso você deve ativar um provedor de configuração de ER no espaço de trabalho **Relatório eletrônico** antes de começar a adicionar ou editar configurações de ER.

> [!NOTE]
> Somente o proprietário de uma configuração de ER pode editá-la. Assim, para que uma configuração de ER possa ser editada, o provedor de configuração de ER apropriado deve estar ativado no espaço de trabalho **Relatório eletrônico**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Examinar a lista de provedores de configuração de ER

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Provedores de configuração**.
3. Na página **Tabela de provedores de configuração**, cada registro de provedor tem um nome e uma URL exclusivos. Examine o conteúdo dessa página. Se já existir um registro para **Litware, Ltda.** (`https://www.litware.com`), ignore o próximo procedimento, [Adicionar um novo provedor de configuração de ER](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>Adicionar um novo provedor de configuração de ER

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Provedores de configuração**.
3. Na página **Provedores de configuração**, selecione **Novo**.
4. No campo **Nome**, insira **Litware, Ltda.**
5. No campo **Endereço na Internet**, insira `https://www.litware.com`.
6. Selecione **Salvar**.

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Ativar um provedor de configuração de ER

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Provedores de configuração**, selecione o bloco **Litware, Ltda.** e, depois, **Definir como ativo**.

Para obter mais informações sobre provedores de configuração de ER, consulte [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>Importar as configurações do formato de ER padrão

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat1"></a>Importar as configurações de ER padrão

Para adicionar as configurações de ER padrão à instância atual do Microsoft Dynamics 365 Finance, você deve importá-las do [repositório](general-electronic-reporting.md#Repository) de ER configurado para essa instância.

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Provedores de configuração**, selecione o bloco **Microsoft** e, depois, selecione **Repositórios** para ver a lista de repositórios do provedor Microsoft.
3. Na página **Repositórios de configuração**, selecione o repositório do tipo **Global** e, depois, selecione **Abrir**. Se você precisar de autorização para se conectar ao Regulatory Configuration Service, siga as instruções de autorização.
4. Na página **Repositório de configuração**, na árvore de configuração no painel esquerdo, selecione a configuração de formato **BACS (Reino Unido)**.
5. Na FastTab **Versões**, selecione a versão **1.1** da configuração do formato de ER selecionada.
6. Selecione **Importar** para baixar a versão selecionada do repositório global para a instância atual do Finance.

![Página do repositório de configuração.](./media/er-quick-start2-import-solution1.png)

> [!TIP]
> Se você tiver problemas para acessar o [repositório global](er-download-configurations-global-repo.md), poderá [baixar configurações](download-electronic-reporting-configuration-lcs.md) do Microsoft Dynamics Lifecycle Services (LCS).

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>Examinar as configurações de ER importadas

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Configurações**, selecione o título **Configurações de relatórios**.
3. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de pagamento**.
4. Observe que, além do formato de ER **BACS (Reino Unido)** selecionado, outras configurações de ER necessárias foram importadas. Verifique se as seguintes configurações de ER estão disponíveis na árvore de configuração:

    - **Modelo de pagamento** – Esta configuração contém o componente de ER [modelo de dados](general-electronic-reporting.md#data-model-and-model-mapping-components) que representa a estrutura de dados do domínio corporativo de pagamento.
    - **Mapeamento de modelos de pagamento 1611** – Esta configuração contém o componente de ER [mapeamento de modelos](general-electronic-reporting.md#data-model-and-model-mapping-components) que descreve como o modelo de dados é preenchido com dados de aplicativos em tempo de execução.
    - **BACS (Reino Unido)** – Esta configuração contém os componentes de ER [formato](general-electronic-reporting.md#FormatComponentOutbound) e mapeamento de formato. O componente de formato especifica o layout do relatório. O componente mapeamento de formato contém a fonte de dados do modelo e especifica como o layout do relatório é preenchido usando essa fonte de dados no tempo de execução.

![Página Configurações.](./media/er-quick-start2-imported-solution1.png)

## <a name="prepare-a-vendor-payment-for-processing"></a><a id="PrepareVendorPayment"></a>Preparar um pagamento de fornecedor para processamento

### <a name="add-bank-information-for-a-vendor-account"></a><a id="AddBankAccount"></a>Adicionar informações bancárias de uma conta de fornecedor

Você deve adicionar as informações bancárias de uma conta de fornecedor que será mencionada posteriormente em um pagamento registrado.

1. Acesse **Contas a pagar** \> **Fornecedores** \> **Todos os fornecedores**.
2. Na página **Todos os fornecedores**, selecione a conta de fornecedor **GB_SI_000001** e, depois, no Painel de Ação, na guia **Fornecedor**, no grupo **Configurar**, selecione **Contas bancárias**.
3. Na página **Contas bancárias do fornecedor**, selecione **Novo** e insira as seguintes informações:

    1. No campo **Conta bancária**, insira **GBP OPER**.
    2. No campo **Grupos bancários**, selecione **BankGBP**.
    3. No campo **Número da conta bancária**, insira **202015**.
    4. No campo **Código SWIFT**, insira <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.
    5. No campo **IBAN**, insira **GB33BUKB20201555555555**.
    6. No campo **Número identificador do banco**, mantenha o valor padrão, <a id="DefineRoutingNumber"></a>**123456**.

    ![Página Contas bancárias do fornecedor.](./media/er-quick-start2-bank-account.png)

4. Selecione **Salvar**.
5. Feche a página.
6. Na página **Todos os fornecedores**, abra a conta do fornecedor **GB_SI_000001**.
7. Na página de detalhes do fornecedor, selecione **Editar** para tornar a página editável, se necessário.
8. Na FastTab **Pagamento** , no campo **Conta bancária**, selecione **GBP OPER**.

    ![Página Detalhes do fornecedor.](./media/er-quick-start2-bank-account-reference.png)

9. Selecione **Salvar**.
10. Feche a página.

### <a name="enter-a-vendor-payment"></a><a id="EnterVendorPayment"></a>Inserir um pagamento de fornecedor

Você deve inserir um novo pagamento de fornecedor usando uma [proposta de pagamento](../../../finance/accounts-payable/create-vendor-payments-payment-proposal.md).

1. Acesse **Contas a pagar** \> **Pagamentos** \> **Diário de pagamentos do fornecedor**.
2. Na página **Diário de pagamentos do fornecedor**, selecione **Novo**.
3. No campo **Nome**, selecione **VendPay**.
4. Selecione **Linhas**.
5. Selecione **Proposta de pagamento** \> **Criar proposta de pagamento**.
6. Na caixa de diálogo **Proposta de pagamento de fornecedor**, configure as condições para filtrar registros somente da conta de fornecedor **GB_SI_000001** e selecione **OK**.
7. Selecione a linha da fatura **00000007_Inv** e, depois, selecione **Criar pagamento**.

    ![Caixa de diálogo Proposta de pagamento de fornecedor.](./media/er-quick-start2-payment-proposal.png)

8. Verifique se o pagamento inserido está configurado para usar o método de pagamento **Eletrônico**.

    ![Página Pagamentos de fornecedor.](./media/er-quick-start2-payment-line.png)

## <a name="process-a-vendor-payment-by-using-the-standard-er-format"></a><a id="ProcessVendorPayment1"></a>Processar um pagamento de fornecedor usando o formato de ER padrão

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment1"></a>Configurar o método de pagamento eletrônico

Você deve configurar o método de pagamento eletrônico para que ele use a configuração do formato de ER importado.

1. Acesse **Contas a pagar** \> **Configuração de pagamento** \> **Métodos de pagamento**.
2. Na página **Métodos de pagamento - Fornecedores**, selecione o método de pagamento **Eletrônico** no painel esquerdo.
3. Selecione **Editar**.
4. Na FastTab **Formatos de arquivo**, defina a opção **Formato de exportação eletrônico geral** como **Sim**.
5. No campo **Exportar configuração de formato**, selecione a configuração de formato **BACS (Reino Unido)**.

    ![Página Métodos de pagamento - Fornecedores.](./media/er-quick-start2-method-of-payment1.png)

6. Selecione **Salvar**.

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment1"></a>Processar um pagamento de fornecedor

1. Acesse **Contas a pagar** \> **Pagamentos** \> **Diário de pagamentos do fornecedor**.
2. Na página **Diário de pagamentos do fornecedor**, selecione o diário de pagamento adicionado inicialmente e, depois, **Linhas**.
3. Na página **Pagamentos de fornecedores**, selecione **Gerar pagamentos**.
4. Na caixa de diálogo **Gerar pagamentos**, insira as seguintes informações:

    - No campo **Método de pagamento**, selecione **Eletrônico**.
    - No campo **Conta bancária**, selecione **GBSI OPER**.

5. Selecione **OK**.
6. Na caixa de diálogo **Parâmetros de relatório eletrônico**, defina a opção **Imprimir relatório de controle** como **Sim** e selecione **OK**.

    ![Página Parâmetros de relatório eletrônico.](./media/er-quick-start2-payment-dialog1.png)

    > [!NOTE]
    > Além do arquivo de pagamento, agora é possível gerar o relatório de controle.

7. Baixe o arquivo zip e extraia os seguintes arquivos dele:

    - O relatório de controle no formato Excel
    - O arquivo de pagamento no formato TXT

        Observe que, de acordo com a [estrutura](#PositionRoutingNumber) do formato de ER fornecido, a linha de pagamento no arquivo gerado começa com o número identificador do banco que foi [definido](#DefineRoutingNumber) para a conta bancária configurada.

        ![Arquivo de pagamento no formato TXT.](./media/er-quick-start2-payment-file1.png)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>Personalizar o formato de ER padrão

Para o exemplo mostrado nesta seção, você quer usar as configurações de ER fornecidas pela Microsoft para gerar arquivos de pagamento de fornecedor no formato BACS, mas deve adicionar uma personalização para dar suporte aos requisitos de um banco específico. Você também quer poder atualizar o formato personalizado quando novas versões das configurações de ER são disponibilizadas. No entanto, você quer atualizar pelo menor custo.

Neste caso, como representante da Litware, Ltda., você deve criar (derivar) uma nova configuração do formato de ER usando como base a configuração **BACS (Reino Unido)** fornecida pela Microsoft.

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>Criar uma formato personalizado

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de pagamento** e selecione **BACS (Reino Unido)**. A Litware, Ltda. usará a versão 1.1 dessa configuração do formato de ER como base para a versão personalizada.
3. Selecione **Criar configuração** para abrir a caixa de diálogo suspensa. Você pode usar essa caixa de diálogo para criar uma nova configuração para um formato de pagamento personalizado.
4. No grupo de campos **Novo**, selecione a opção **Derivar de Nome: BACS (Reino Unido), Microsoft**.
5. No campo **Nome**, insira **BACS (personalizado do Reino Unido)**.

    ![Caixa de diálogo suspensa Criar configuração.](./media/er-quick-start2-add-derived-format.png)

6. Selecione **Criar configuração**.

A versão 1.1.1 da configuração do formato de ER **BACS (personalizado do Reino Unido)** foi criada. Essa versão tem um [status](general-electronic-reporting.md#component-versioning) de **Rascunho** e pode ser editada. O conteúdo atual do formato de ER personalizado corresponde ao conteúdo do formato fornecido pela Microsoft.

![Página Configurações.](./media/er-quick-start2-derived-format-configuration1.png)

### <a name="edit-a-custom-format"></a><a id="ConfigureDerivedFormat"></a>Editar uma formato personalizado

Você deve configurar um formato personalizado de modo que ele atenda a requisitos específicos do banco. Por exemplo, um banco pode exigir que os arquivos de pagamento gerados incluam o código SWIFT (Society for Worldwide Interbank Financial Telecommunication) de um banco que tem a função de agente no pagamento de fornecedor processado. Os códigos SWIFT são códigos bancários internacionais que identificam bancos específicos em todo o mundo. Também são conhecidos como códigos identificadores bancários (BICs). O código SWIFT deve ter 11 caracteres e deve ser inserido no início de cada linha de pagamento em um arquivo de pagamento gerado.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de pagamento** e selecione **BACS (personalizado do Reino Unido)**.
3. Na FastTab **Versões**, selecione a versão **1.1.1** da configuração selecionada.
4. Selecione **Designer**.
5. Na página **Designer de formato**, selecione **Mostrar detalhes** para ver mais informações sobre os elementos de formato.
6. Expanda e examine os seguintes elementos:

    - O elemento **BACSReportsFolder** do tipo **Pasta**. Esse elemento é usado para gerar saída no formato ZIP.
    - O elemento **arquivo** do tipo **Arquivo**. Esse elemento é usado para gerar um arquivo de pagamento no formato TXT.
    - O elemento **transações** do tipo **Sequência**. Esse elemento é usado para gerar uma única linha de pagamento em um arquivo de pagamento.
    - O elemento **transação** do tipo **Sequência**. Esse elemento é usado para gerar campos individuais de uma única linha de pagamento.

7. Selecione o elemento **transação**.

    ![Elemento transação no designer de operações de ER.](./media/er-quick-start2-derived-format0.png)

    > [!NOTE]
    > O relatório fornecido é configurado de forma que <a id="PositionRoutingNumber"></a>todas as linhas de pagamento comecem com o número identificador do banco. O elemento de formato **vendBankRouteNum** é usado para essa finalidade. 

8. Selecione **Adicionar** e, depois, selecione o tipo **Texto\\Sequência de caracteres** do elemento de formato que você está adicionando:

    1. No campo **Nome**, insira **vendBankSWIFT**.
    2. No campo **Comprimento mínimo**, insira **"11**.
    3. No campo **Comprimento máximo**, insira **11**.
    4. Selecione **OK**.

    > [!NOTE]
    > O elemento **vendBankSWIFT** será usado para inserir o código SWIFT de um banco de fornecedor nos arquivos gerados.

9. Na árvore de estrutura de formato, selecione **vendBankSWIFT**.
10. Selecione **Mover para cima** para mover o elemento de formato selecionado um nível acima. Repita esta etapa até que o elemento **vendBankSWIFT** seja o <a id="PositionSWIFTCode"></a>primeiro elemento no elemento pai **transação**.

    ![VendBankSWIFT como o primeiro elemento em transação no designer de operações de ER.](./media/er-quick-start2-derived-format1.png)

11. Enquanto **vendBankSWIFT** ainda estiver selecionado na árvore de estrutura de formato, selecione a guia **Mapeamento** e expanda a fonte de dados **modelo**.
12. Expanda **model.Payment** \> **model.Payment.CreditorAgent** e selecione o campo de fonte de dados **model.Payment.CreditorAgent.BICFI**. Este campo de fonte de dados expõe o código SWIFT de um banco de fornecedor ao qual foi atribuída a função de agente no pagamento de fornecedor processado.
13. Selecione **Associar**. Agora o elemento de formato **vendBankSWIFT** está associado ao campo de fonte de dados **model.Payment.CreditorAgent.BICFI**, de forma que os códigos SWIFT serão inseridos nos arquivos de pagamento gerados.

    ![Elemento de formato vendBankSWIFT associado ao campo de fonte de dados model.Payment.CreditorAgent.BICFI no designer de operações de ER.](./media/er-quick-start2-derived-format2.png)

14. Selecione **Salvar**.
15. Feche a página do designer.

### <a name="mark-a-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>Marcar um formato personalizado como executável

Agora que a primeira versão do formato personalizado foi criada e tem o status de **Rascunho**, você pode executá-la para fins de teste. Para executar o relatório, você deve processar um pagamento de fornecedor usando o método de pagamento que se refere ao seu formato de ER personalizado. Por padrão, quando você chama um formato de ER no aplicativo, somente as versões que têm o status **Concluída** ou **Compartilhada** são [consideradas](general-electronic-reporting.md#component-versioning). Esse comportamento ajuda a impedir que formatos de ER com designs não concluídos sejam utilizados. No entanto, para as execuções de teste, você pode forçar o aplicativo a usar a versão do seu formato de ER que tem o status de **Rascunho**. Dessa forma, é possível ajustar a versão do formato atual se modificações forem necessárias. Para obter mais informações, consulte [Aplicabilidade](electronic-reporting-destinations.md#applicability).

Para usar a versão de rascunho de um formato de ER, você deve marcar o formato de ER explicitamente.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3. Na caixa de diálogo **Parâmetros de usuário**, defina a opção **Executar configurações** como **Sim** e selecione **OK**.
4. Selecione **Editar** para tornar a página atual editável, conforme necessário.
5. Na árvore de configuração no painel esquerdo, selecione **BACS (personalizado do Reino Unido)**.
6. Defina a opção **Executar Rascunho** como **Sim**.

    ![Opção Executar Rascunho na página Configurações.](./media/er-quick-start2-derived-format-configuration2.png)

## <a name="process-a-vendor-payment-by-using-the-custom-er-format"></a><a id="ProcessVendorPayment2"></a>Processar um pagamento de fornecedor usando o formato de ER personalizado

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment2"></a>Configurar o método de pagamento eletrônico

Você deve configurar o método de pagamento eletrônico para que seu formato de ER personalizado seja usado para processar pagamentos de fornecedor.

1. Acesse **Contas a pagar** \> **Configuração de pagamento** \> **Métodos de pagamento**.
2. Na página **Métodos de pagamento - Fornecedores**, selecione o método de pagamento **Eletrônico** no painel esquerdo.
3. Selecione **Editar**.
4. Na FastTab **Formato de arquivo**, defina a opção **Formato de exportação eletrônico geral** como **Sim**.
5. No campo **Exportar configuração de formato**, selecione a configuração de formato **BACS (personalizado do Reino Unido)**.

    ![Página Métodos de pagamento - Fornecedores.](./media/er-quick-start2-method-of-payment2.png)

6. Selecione **Salvar**.

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment2"></a>Processar um pagamento de fornecedor

1. Acesse **Contas a pagar** \> **Pagamentos** \> **Diário de pagamentos do fornecedor**.
2. Na página **Diário de pagamentos do fornecedor**, selecione o diário de pagamento que você criou anteriormente.
3. Selecione **Linhas**.
4. Na página **Pagamentos de fornecedores**, acima da grade, selecione **Status do pagamento** \> **Nenhum**.
5. Selecione **Gerar pagamento**.
6. Na caixa de diálogo **Gerar pagamentos**, insira as seguintes informações:

    - No campo **Método de pagamento**, selecione **Eletrônico**.
    - No campo **Conta bancária**, selecione **GBSI OPER**.

7. Selecione **OK**.
8. Na caixa de diálogo **Parâmetros de relatório eletrônico**, defina a opção **Imprimir relatório de controle** como **Sim** e selecione **OK**.

    > [!NOTE]
    > Além do arquivo de pagamento, você só pode gerar o relatório de controle.

9. Baixe o arquivo zip e extraia os seguintes arquivos dele:

    - O relatório de controle no formato Excel
    - O arquivo de pagamento no formato TXT

        Observe que, de acordo com a estrutura do seu formato de ER personalizado, agora a linha de pagamento no arquivo gerado [começa](#PositionSWIFTCode) com o código Swift que foi [inserido](#DefineSWIFTCode) para a conta bancária do fornecedor cujo pagamento foi processado.

        ![Arquivo de pagamento no formato TXT.](./media/er-quick-start2-payment-file2.png)

## <a name="import-new-versions-of-the-standard-er-format-configurations"></a><a id="ImportERSolution2"></a>Importar novas versões das configurações do formato de ER padrão

Para o exemplo mostrado nesta seção, você recebe uma notificação sobre o artigo da Base de Dados de Conhecimento [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046). Essa notificação informa sobre a nova versão do formato de ER **BACS (Reino Unido)** publicada pela Microsoft. Além do relatório de controle, essa nova versão permite que os usuários gerem o relatório de aviso de pagamento e o relatório de nota de participação enquanto um pagamento de fornecedor estiver sendo processado. Você quer começar a usar essa funcionalidade.

### <a name="import-new-versions-of-the-standard-er-configurations"></a><a id="ImportERFormat2"></a>Importar novas versões das configurações de ER padrão

Para adicionar novas versões das configurações de ER à instância atual do Finance, você deve importá-las do [repositório](general-electronic-reporting.md#Repository) de ER que configurou.

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Provedores de configuração**, selecione o bloco **Microsoft** e, depois, selecione **Repositórios** para ver a lista de repositórios do provedor Microsoft.
3. Na página **Repositórios de configuração**, selecione o repositório do tipo **Global** e, depois, selecione **Abrir**. Se você precisar de autorização para se conectar ao Regulatory Configuration Service, siga as instruções de autorização.
4. Na página **Repositório de configuração**, na árvore de configuração no painel esquerdo, selecione a configuração de formato **BACS (Reino Unido)**.
5. Na FastTab **Versões**, selecione a versão **3.3** da configuração do formato de ER selecionada.
6. Selecione **Importar** para baixar a versão selecionada do repositório global para a instância atual do Finance.

![Página do repositório de configuração.](./media/er-quick-start2-import-solution2.png)

> [!TIP]
> Se você tiver problemas para acessar o [repositório global](er-download-configurations-global-repo.md), poderá [baixar configurações](download-electronic-reporting-configuration-lcs.md) do LCS.

### <a name="review-the-imported-er-format-configurations"></a><a id="ReviewImportedERFormat"></a>Examinar as configurações do formato de ER importado

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Configurações**, selecione o título **Configurações de relatórios**.
3. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de pagamento** e selecione **BACS (Reino Unido)**.
4. Na Guia Rápida **Versões**, selecione a versão **3.3**.
5. Selecione **Designer**.
6. Na página **Designer de formato**, expanda o elemento de formato **BACSReportsFolder**.
7.  Observe que a versão 3.3 contém o elemento de formato **PaymentAdviceReport** usado para gerar um relatório de aviso de pagamento quando um pagamento de fornecedor é processado.

    ![Elemento de formato PaymentAdviceReport no designer de operações de ER.](./media/er-quick-start2-imported-solution2.png)

8. Feche a página do designer.

## <a name="adopt-the-changes-in-the-new-version-of-an-imported-format-in-a-custom-format"></a><a id="AdoptNewBaseVersion"></a>Adotar as alterações na nova versão de um formato importado em um formato personalizado

### <a name="complete-the-current-draft-version-of-a-custom-format"></a><a id="CompleteDerivedFormat"></a>Concluir a versão de rascunho atual de um formato personalizado

Se você quiser manter o estado atual do seu formato personalizado, conclua a versão de rascunho 1.1.1 alterando o status de **Rascunho** para **Concluído**.

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Configurações**, selecione o título **Configurações de relatórios**.
3. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de pagamento**, expanda **BACS (Reino Unido)** e selecione **BACS (personalizado do Reino Unido)**.
4. Na FastTab **Versões**, selecione **Alterar status** \> **Concluído** e clique em **OK**.

O status da versão 1.1.1 muda de **Rascunho** para **Concluído** e a versão se torna somente leitura. Uma nova versão editável, 1.1.2, foi adicionada e tem o status de **Rascunho**. Você pode usar essa versão para fazer outras alterações no formato de ER personalizado.

### <a name="rebase-a-custom-format-to-a-new-base-version"></a><a id="RebaseDerivedFormat"></a>Trocar base de um formato personalizado para uma nova versão base

Para começar a usar a nova funcionalidade da versão 3.3 do formato **BACS (Reino Unido)** na sua personalização, você deve alterar a versão de configuração base da configuração personalizada, **BACS (personalizado do Reino Unido)**. Esse processo é conhecido como [troca de base](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase). Em vez da versão 1.1 de **BACS (Reino Unido)**, use a versão 3.3.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de pagamento** e selecione **BACS (personalizado do Reino Unido)**.
3. Na FastTab **Versões**, selecione a versão **1.1.2** e, depois, **Trocar base**.
4. Na caixa de diálogo **Trocar base**, no campo **Versão de destino**, selecione a versão **3.3** da configuração base para aplicá-la como a nova base e usá-la para atualizar a configuração.

    ![Caixa de diálogo Trocar base.](./media/er-quick-start2-rebase1.png)

5. Selecione **OK**.
6. Observe que o número da versão de rascunho foi alterado de **1.1.2** para **3.3.2** para refletir a mudança na versão base.

    Quando a versão personalizada e uma nova versão base são mescladas, podem surgir alguns conflitos por causa de alterações no formato que não podem ser mescladas automaticamente.

    ![Configuração de base trocada com conflitos na página Configurações.](./media/er-quick-start2-rebase2.png)

    Se forem detectados conflitos, eles deverão ser resolvidos manualmente no designer de formato.

7. Na Guia Rápida **Versões**, selecione a versão **3.3.2**.
8. Selecione **Designer**.
9. Na página **Designer de formato**, na FastTab **Detalhes**, selecione um registro de conflito de troca de base e selecione **Aplicar valor base**.

    ![Registro de conflito de troca de base no designer de operações de ER.](./media/er-quick-start2-rebase3.png)

10. Selecione **Salvar**.

    O registro do conflito de troca de base não deve mais aparecer na FastTab **Detalhes**.

    ![Conflito resolvido no designer de operações de ER.](./media/er-quick-start2-rebase4.png)

    > [!NOTE]
    > Você resolveu o conflito confirmando que a versão 3 do modelo base deve ser usada neste formato de ER.

11. Expanda **BACSReportsFolder** \> **arquivo** \> **transações** \> **transação**.
12. Na guia **Mapeamento**, observe que a versão 3.3.2 do seu formato de ER personalizado contém sua personalização (o elemento de formato **vendBankSWIFT** e sua associação) e a nova funcionalidade da versão 3.3 do formato de ER base fornecido pela Microsoft (o elemento de formato **PaymentAdviceReport** junto com os elementos aninhados e associações configuradas). Com apenas alguns cliques do mouse, você adotou as modificações de uma nova versão base mesclando-as com sua personalização.

    ![Formato mesclado no designer de operações de ER.](./media/er-quick-start2-rebase5.png)

13. Feche a página do designer.

> [!NOTE]
> A ação de troca de base é reversível. Para cancelar essa troca de base, selecione a versão **1.1.1** do formato **BACS (personalizado do Reino Unido)** na FastTab **Versões** e selecione **Obter esta versão**. A versão 3.3.2 será renumerada para 1.1.2, e o conteúdo da versão de rascunho 1.1.2 será compatível com o conteúdo da versão 1.1.1.

### <a name="process-a-vendor-payment-by-using-a-rebased-er-format"></a><a id="ProcessPayment3"></a>Processar um pagamento de fornecedor usando o formato de ER com troca de base

1. Acesse **Contas a pagar** \> **Pagamentos** \> **Diário de pagamentos do fornecedor**.
2. Na página **Diário de pagamentos do fornecedor**, selecione o diário de pagamento que você criou anteriormente.
3. Selecione **Linhas**.
4. Na página **Pagamentos de fornecedores**, acima da grade, selecione **Status do pagamento** \> **Nenhum**.
5. Selecione **Gerar pagamento**.
6. Na caixa de diálogo **Gerar pagamentos**, insira as seguintes informações:

    - No campo **Método de pagamento**, selecione **Eletrônico**.
    - No campo **Conta bancária**, selecione **GBSI OPER**.

7. Selecione **OK**.
8. Na caixa de diálogo **Parâmetros de relatório eletrônico**, insira as seguintes informações:

    - Defina a opção **Imprimir relatório de controle** como **Sim**.
    - Defina a opção **Imprimir aviso de pagamento** como **Sim**.

    ![Caixa de diálogo Parâmetros de relatório eletrônico.](./media/er-quick-start2-payment-dialog2.png)

    > [!NOTE]
    > Além do arquivo de pagamento, agora é possível gerar o relatório de controle e o relatório de aviso de pagamento.

9. Selecione **OK**.
10. Baixe o arquivo zip e extraia os seguintes arquivos dele:

    - O relatório de controle no formato Excel
    - O relatório de aviso de pagamento no formato Excel

        ![Relatório de aviso de pagamento no formato Excel.](./media/er-quick-start2-payment-advice-report.png)

    - O arquivo de pagamento no formato TXT

        Observe que a linha de pagamento no arquivo gerado começa com o código Swift que foi inserido para a conta bancária de um fornecedor cujo pagamento foi processado.

        ![Arquivo de pagamento no formato TXT.](./media/er-quick-start2-payment-file3.png)

## <a name="additional-resources"></a><a id="References"></a>Recursos adicionais

- [Visão geral do Relatório Eletrônico](general-electronic-reporting.md)
- [Baixar configurações de ER do Lifecycle Services](download-electronic-reporting-configuration-lcs.md)
- [Baixar configurações de ER do repositório global de serviço de configuração](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]