---
title: Processamento de recibo de despesas
description: Este tópico fornece informações sobre o processamento de OCR (reconhecimento óptico de caracteres) para recibos. Esse recurso foi desenvolvido para melhorar a experiência do usuário quando os relatórios de despesas são criados no Microsoft Dynamics 365 Finance.
author: stsporen
manager: AnnBe
ms.date: 11/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: stsporen
ms.search.validFrom: 2019-11-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 49cdfeac8cda9f1ddd3aca61f902f00f30f3485b
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154031"
---
# <a name="expense-receipt-processing"></a>Processamento de recebimento de despesas

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


A entrada de despesas foi aprimorada por meio da introdução do processamento de OCR (reconhecimento óptico de caracteres) para recibos. Esse recurso foi desenvolvido para melhorar a experiência do usuário quando os relatórios de despesas são criados.

## <a name="key-features"></a>Recursos principais

- O nome do comerciante, a data e o valor total são extraídos dos recibos.
- O recurso tenta fazer a correspondência entre os recibos não anexados e as transações de despesa não anexadas.
- Os usuários podem criar transações de despesa inseridas manualmente usando os recibos.

## <a name="usage-examples"></a>Exemplos de uso

- **Anexar automaticamente os recibos que incluem transações de cartão de crédito quando um relatório de despesas é criado.**

    1. Abra o espaço de trabalho **Gerenciamento de despesas**.
    2. Na guia **Recibos**, verifique se há recibos não anexados. Também é possível carregar recibos na guia **Recibos**.
    3. Na guia **Despesas**, verifique se há despesas não anexadas. Normalmente, o administrador de despesas importa essas despesas do emissor do cartão de crédito.
    4. Selecione **Novo relatório de despesa**. Observe que agora você também pode incluir despesas, e recibos, ao criar um relatório de despesas. Se você adicionar despesas e recibos, será disparada a correspondência automática de recibos em relação às despesas.

- **Criar uma despesa ou fazer a correspondência de uma despesa usando um recibo.**

    1. Em um relatório de despesas, na guia **Recibos**, anexe um recibo selecionando **Adicionar recibos**.
    2. Na imagem carregada do recibo, observe as opções **Criar** e **Fazer a Correspondência**.

        - Selecione **Criar** para criar uma transação de despesa inserida manualmente e preencher os valores que são extraídos do recibo.
        - Se você selecionar **Fazer a Correspondência**, o sistema tentará fazer a correspondência de uma despesa existente com o recibo.

## <a name="installation"></a>Instalação

Esse recurso funciona em combinação com o recurso **Relatórios de despesas reformulados** para ajudar a simplificar a experiência de despesas.

Para usar esses recursos avançados de despesa, instale o suplemento Serviço de Gerenciamento de Despesas para o Microsoft Dynamics 365 Finance e ative os recursos na sua instância. Você pode acessar o suplemento do seu projeto no Microsoft Dynamics Lifecycle Services (LCS).

1. Entre no LCS e abra o ambiente desejado.
2. Vá para **Detalhes completos**.
3. Selecione **Manter** ou role para baixo até a Guia Rápida **Suplementos de ambiente**.
4. Selecione **Instalar um novo suplemento**.
5. Selecione **Serviço de Gerenciamento de Despesas**.
6. Acompanhe o guia de instalação e concorde com os termos e condições.
7. Selecione **Instalar**.

No espaço de trabalho **Gerenciamento de recursos**, ative os seguintes recursos:

- Relatórios de despesas reformulados
- Corresponder automaticamente e criar despesa a partir do recibo

Quando você ativa esses recursos, as seguintes ações ocorrem:

- O espaço de trabalho existente **Gerenciamento de despesas** é substituído pelo novo espaço de trabalho.
- Um novo item de menu para visibilidade do campo de despesa é adicionado.
- Você ainda pode abrir a página **Relatórios de despesas** antiga acessando **Gerenciamento de despesas > Minhas despesas > Relatórios de despesas**.
- Fluxos de trabalho e quaisquer aprovações ainda o levam para a página de relatórios de despesas existente.
- Os recibos serão processados pelo Microsoft Azure Cognitive Services, e metadados serão extraídos e adicionados.
- É adicionada uma opção que permite a você criar um relatório de despesas que inclua recibos não anexados correspondidos.
- Uma opção que foi adicionada aos relatórios de despesas permite criar uma linha de despesa a partir de um recibo ou tenta fazer a correspondência de um recibo existente com uma linha de despesa existente.

Para obter mais informações sobre o recurso Relatórios de despesas reformulados, consulte [Relatórios de despesas reformulados](ExpenseWorkspaceNew.md).

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**A Microsoft usa meus dados para seus modelos?**

Não, a Microsoft criou um modelo geral de aprendizado de máquina para o serviço de processamento de recibos. Esse modelo não se baseia nos recibos que você carrega.

**Onde esse recurso está disponível e é processado?**

Atualmente, nos Estados Unidos.

**Para onde vão meus recibos?**

O Finance entrará em contato com o Cognitive Services para extrair os dados de campo. O Cognitive Services manterá uma cópia do seu recibo por até 24 horas enquanto ocorre o processamento. Depois que o processamento for concluído, o Cognitive Services removerá o recibo. Os recibos continuam armazenados no Finance.

Para obter mais informações, consulte [Habilitar o conhecimento de recibo com o novo recurso do Reconhecimento de Formulários](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).
