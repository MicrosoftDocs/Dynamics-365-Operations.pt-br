---
title: Configurar destinos de ER dependentes da ação
description: Este artigo explica como configurar destinos dependentes da ação para um formato de ER (Relatório eletrônico) que está configurado para gerar documentos de saída.
author: kfend
ms.date: 12/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.form: ERSolutionTable, ERFormatDestinationTable
ms.openlocfilehash: 80a432a431891c02e4bf5c71cfe2bd9642c41c75
ms.sourcegitcommit: e9000d0716f7fa45175b03477c533a9df2bfe96d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2022
ms.locfileid: "9843788"
---
# <a name="configure-action-dependent-er-destinations"></a>Configurar destinos de ER dependentes da ação

[!include [banner](../includes/banner.md)]

Você pode configurar [destinos](electronic-reporting-destinations.md) para cada componente de saída (pasta ou arquivo) de uma [configuração](general-electronic-reporting.md#Configuration) de formato de [Relatório Eletrônico (ER)](general-electronic-reporting.md) usada para gerar um documento de saída. Os usuários que executam um formato de ER deste tipo e que têm direitos de acesso apropriados também podem alterar as configurações de destino configuradas no tempo de execução.

No Microsoft Microsoft Dynamics 365 Finance **versão 10.0.17 e posterior**, um formato de ER pode ser executado ao [provisionar](er-apis-app10-0-17.md) um código de ação executado pelo usuário executando o formato de ER. Por exemplo, no módulo **Contas a receber**, nas configurações de gerenciamento de impressão, você pode selecionar um formato de ER que gera um documento comercial específico, como uma fatura de texto livre. Em seguida, você poderá selecionar **Exibir** para exibir a fatura ou a **Impressão** e enviá-la para uma impressora. Se uma ação do usuário for aprovada para o formato de ER em execução no tempo de execução, você poderá configurar diferentes destinos de ER para diferentes ações do usuário. Este artigo explica como configurar destinos de ER para este tipo de formato de ER.

## <a name="make-action-dependent-er-destinations-available"></a>Disponibilizar destinos de ER dependentes da ação

Para configurar destinos de ER dependentes da ação na atual instância do Finance e habilitar a [nova](er-apis-app10-0-17.md) API de ER, abra o espaço de trabalho [Gerenciamento de recursos](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace) e ative o recurso **Configurar destinos específicos a serem usados para e diferentes ações de PM**. Para usar destinos de ER configurados para relatórios em runtime, habilite o recurso **Rotear a saída de relatórios de PM com base em destinos de ER que são específicos à ação do (ciclo 1)**.

## <a name="configure-action-dependent-er-destinations"></a>Configurar destinos de ER dependentes da ação

Ao ativar o recurso **Configurar destinos de ER específicos a serem usados para diferentes ações de PM**, você pode configurar destinos de ER dependentes da ação na guia **Destino do arquivo** da página **Destino do relatório eletrônico**. Para cada componente, você pode adicionar um registro e habilitar destinos de ER específicos. Para cada registro, você deve especificar o tipo de documento ao qual os destinos de ER configurados devem ser aplicados. No campo **Tipo de documento**, selecione um dos seguintes valores:

- Selecione **Eletrônico** para aplicar os destinos configurados se nenhum código de ação do usuário for fornecido no runtime.
- Selecione **Gerenciamento de impressão** para aplicar os destinos configurados se um código de ação do usuário for fornecido no runtime.
- Selecione **Qualquer** para sempre aplicar os destinos configurados, independentemente de um código de ação do usuário ter sido fornecido no runtime.

Se você selecionar o tipo de documento **Gerenciamento de impressão**, deverá especificar as ações de usuário às quais os destinos de ER configurados devem ser aplicados. No campo **Ação de gerenciamento de impressão**, selecione um dos valores a seguir:

- Selecione **Exibir** para aplicar os destinos configurados se a ação de usuário **Exibir** for fornecida no runtime.
- Selecione **Imprimir** para aplicar os destinos configurados se a ação de usuário **Imprimir** for fornecida no runtime.
- Selecione **Enviar** para aplicar os destinos configurados se a ação de usuário **Enviar** for fornecida no runtime.

> [!NOTE]
> Várias ações podem ser selecionadas para um único registro de destino.

Se você selecionar o tipo de documento **Qualquer**, a **Detecção automática** será automaticamente selecionada no campo **Ação de gerenciamento de impressão** como uma ação do usuário, e o seguinte comportamento ocorrerá:

- Se nenhum código de ação do usuário for fornecido no runtime, os destinos de ER configurados serão aplicados.
- Se um código de ação do usuário for fornecido no runtime, será aplicado um destino de ER predefinido para uma ação específica, **independentemente de ela ter sido habilitada**:

    - Quando a ação **Exibir** é fornecida no runtime, o destino de ER **Tela** é aplicado.
    - Quando a ação **Exibir** é fornecida no runtime, o destino de ER **Tela** é aplicado.
    - Quando a ação **Imprimir** é fornecida no runtime, o destino de ER **Imprimir** é aplicado.

Por exemplo, você pode usar o formato de ER **Fatura de texto livre (Excel)** para imprimir uma [fatura de texto livre](../../../finance/accounts-receivable/create-free-text-invoice-new.md) ao lançá-la. Para rotear um documento gerado, você deve configurar os destinos de ER para esse formato de ER. Por exemplo, pode ser necessário configurar esses destinos de ER para executar o seguinte em um documento gerado:

- Arquive o documento se o formato de ER for executado, mas nenhum código de ação for fornecido (por exemplo, quando o documento for enviado eletronicamente).
- Visualize o documento em um navegador da Web quando um usuário executar a ação **Exibir**.
- Arquivar e imprimir o documento quando um usuário realizar a ação **Imprimir**.
- Arquive o documento e envie-o por email como o anexo de uma mensagem de email de saída quando um usuário executar a ação **Enviar**.

A ilustração a seguir mostra como é possível configurar destinos de ER como o conjunto de registros de destino individuais quando cada registro é configurado para uma ação individual do usuário:

![Página de destino de relatório eletrônico que tem configurações de destino dependentes de ação para um formato de ER quando cada registro de destino é configurado para uma única ação de usuário.](./media/er-destination-action-dependent-01.png)

A ilustração a seguir mostra como é possível obter o mesmo resultado configurando destinos de ER como o conjunto de registros de destino individuais quando cada registro é configurado para um destino individual:

![EPágina de destino de relatório eletrônico que tem configurações de destino dependentes de ação para um formato de ER quando cada registro de destino é configurado para um único destino.](./media/er-destination-action-dependent-01a.png)

> [!NOTE]
> Se um código de ação for fornecido para o formato ER em execução, mas nenhum destino tiver sido configurado para esse código de ação, o comportamento de destino [padrão](electronic-reporting-destinations.md#default-behavior) será aplicado.

## <a name="change-action-dependent-er-destinations-at-runtime"></a>Alterar destinos de ER dependentes da ação no runtime

Quando um formato de ER é executado, se as ações do usuário foram provisionadas pelos usuários que têm as [permissões apropriadas](electronic-reporting-destinations.md#security-considerations) para alterar as configurações de destino configuradas no runtime, uma caixa de diálogo será exibida, oferecendo a opção de alterar as configurações de destino definidas. Esta caixa de diálogo é opcional e sua aparência depende de como foi implementada a chamada que a estrutura de ER faz para executar um formato de ER. Se esta caixa de diálogo for exibida, os destinos de ER nela serão habilitados de acordo com a ação do usuário fornecida.

A ilustração a seguir mostra um exemplo da caixa de diálogo **Destinos de formato de relatório eletrônico** que aparece quando uma fatura de texto livre é [lançada](../../../finance/accounts-receivable/create-free-text-invoice-new.md) e o formato **Fatura de texto livre (Excel)** é executado para gerar este documento, caso a ação **Impressora** tenha sido configurada e os destinos de ER tenham sido definidos para esse formato, conforme mostrado anteriormente neste artigo.

![Caixa de diálogo que dá a opção de alterar os destinos de ER configurados iniciais para o formato de ER em execução.](./media/er-destination-action-dependent-02.gif)

> [!NOTE]
> Se você configurou destinos de ER para vários componentes do formato de ER em execução, uma opção será oferecida separadamente para cada componente configurado do formato de ER.

Se vários formatos de ER forem aplicáveis como modelos de relatório para o documento selecionado, todos os destinos de ER para todos os modelos de relatório de ER aplicáveis serão mostrados na caixa de diálogo e estarão disponíveis para ajuste manual em runtime.

Se nenhum modelo de relatório do [SSRS (SQL Server Reporting Services)](SSRS-report.md) for aplicável ao documento selecionado, a seleção padrão de destinos do Gerenciamento de impressão será ocultada dinamicamente.

A partir da versão **10.0.31** do Finance, você pode alterar manualmente os destinos de ER atribuídos em runtime para os seguintes documentos comerciais:

- Demonstrativo da conta de cliente
- Nota de juros
- Nota de carta de cobrança
- Aviso de Pagamento de Cliente
- Aviso de Pagamento de Fornecedor

Para ativar a capacidade de alterar destinos de ER em runtime, habilite o recurso **Permitir o ajuste de destinos de ER em runtime** no espaço de trabalho [Gerenciamento de recursos](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace).

> [!IMPORTANT]
> Para os relatórios **Aviso de Pagamento de Cliente** e **Aviso de Pagamento de Fornecedor**, a capacidade de alterar os destinos de ER manualmente só estará disponível se a versão de pré-lançamento de **ForcePrintJobSettings** estiver habilitada.

[![Ajustar destinos de ER em runtime.](./media/ERdestinaiotnChangeUI.jpg)](./media/ERdestinaiotnChangeUI.jpg)

> [!NOTE]
> Quando a opção **Usar destino de gerenciamento de impressão** estiver definida como **Sim**, o sistema usará os destinos padrão de ER configurados para relatórios de ER específicos. Todas as alterações manuais feitas na caixa de diálogo são ignoradas. Defina a opção usar a opção **Usar destino de gerenciamento de impressão** como **Não** para processar documentos para os destinos de ER definidos na caixa de diálogo imediatamente antes de executar os relatórios.

Os documentos comerciais a seguir não assumem a seleção explícita do usuário de uma ação quando são executados:

- Demonstrativo da conta de cliente
- Nota de juros
- Nota de carta de cobrança
- Aviso de Pagamento de Cliente
- Aviso de Pagamento de Fornecedor

A lógica a seguir é usada para determinar qual ação é usada enquanto os relatórios anteriores são processados:

- Se a versão de pré-lançamento **ForcePrintJobSettings** estiver habilitada:

    - Se a opção **Usar o destino de gerenciamento de impressão** estiver definida como **Sim**, a ação **Imprimir** será usada.
    - Se a opção **Usar o destino de gerenciamento de impressão** estiver definida como **Não**, a ação **Exibir** será usada.

- Se a versão de pré-lançamento **ForcePrintJobSettings** não estiver habilitada:

    - Se a opção **Usar destino de gerenciamento de impressão** estiver definida como **Sim**, a ação **Imprimir** será usada para os relatórios **Aviso de Pagamento de Cliente** e **Aviso de Pagamento de Fornecedor**.
    - Se a opção **Usar destino de gerenciamento de impressão** estiver definida como **Não**, o modelo de relatório padrão do SSRS sempre será usado para os relatórios **Aviso de Pagamento de Cliente** e **Aviso de Pagamento de Fornecedor**, independentemente das configurações de ER definidas.
    - A ação **Imprimir** é sempre usada para os relatórios **Demonstrativo da conta de cliente**, **Nota de juros** e **Nota de carta de cobrança**.

Para a lógica anterior, as ações **Imprimir** ou **Exibir** podem ser usadas para configurar destinos de relatório de ER dependentes da ação. Em runtime, somente os destinos de ER configurados para uma ação específica são filtrados na caixa de diálogo.

## <a name="verify-the-provided-user-action"></a>Verificar a ação fornecida pelo usuário

Você pode verificar qual ação do usuário, se houver, é fornecida para a execução do formato de ER ao executar uma ação de usuário específica. Essa verificação é importante quando você deve configurar destinos de ER dependentes da ação, mas não tem certeza sobre qual código de ação do usuário, se houver, é fornecido. Por exemplo, quando você inicia o lançamento de uma nota fiscal de texto livre e define a opção **Imprimir fatura** como **Sim** na caixa de diálogo **Lançar fatura de texto livre**, você pode definir a opção **Usar o destino de gerenciamento de impressão** como **Sim** ou **Não**.

Siga estas etapas para verificar o código de ação do usuário fornecido.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3. Na caixa de diálogo **Parâmetros de usuário**, [defina](er-trace-reports-compare-baseline.md#configure-er-parameters-to-use-the-baseline-feature) a opção **Executar no modo de depuração** como **Sim**.
4. Realizar uma ação do usuário executando um formato de ER. Lembre-se de que os parâmetros de usuário de ER são específico do usuário e da empresa.
5. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Logs de depuração de configuração**.
6. Na página **Logs de depuração de configuração**, filtre os logs de execução de ER para encontrar o log do formato de ER executado.
7. Revise as entradas de log que devem conter o registro que apresenta o código de ação de usuário fornecido, caso alguma ação tenha sido fornecida para o formato de ER ser executado.

    ![Página logs do relatório de execução eletrônica que contém informações sobre o código de ação do usuário que foi fornecido para a execução filtrada de um formato de ER.](./media/er-destination-action-dependent-03.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de Relatório Eletrônico (ER)](general-electronic-reporting.md)

[Destinos de Relatório eletrônico (ER)](electronic-reporting-destinations.md)

[Alterações na API da estrutura do relatório eletrônico para Application update 10.0.17](er-apis-app10-0-17.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
