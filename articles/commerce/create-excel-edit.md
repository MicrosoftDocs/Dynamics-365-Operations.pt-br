---
title: Criar uma pasta de trabalho do Excel para editar transações de varejo
description: Este tópico descreve como criar uma pasta de trabalho do Excel para que você possa editar transações de varejo no Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: b2b6e98db54e7747912aad26f4b8ae24b9ad5a6d
ms.sourcegitcommit: ce51ff2b6099c75dceb99de6dea9d53baf99772d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "4458491"
---
# <a name="create-an-excel-workbook-to-edit-retail-transactions"></a>Criar uma pasta de trabalho do Excel para editar transações de varejo

[!include [banner](../includes/banner.md)]

Este tópico descreve como criar uma pasta de trabalho do Excel para que você possa editar transações de varejo no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Há um modelo de Excel predefinido que os clientes podem acessar de diferentes partes do sistema e usar para editar e auditar transações de varejo. No entanto, os clientes também podem criar uma pasta de trabalho personalizada do Excel para este fim.

## <a name="create-and-configure-an-excel-workbook"></a>Criar e configurar uma pasta de trabalho do Excel

Para criar e configurar uma pasta de trabalho do Excel para que você possa editar transações de varejo, siga estas etapas:

1. Abra o Excel e crie uma pasta de trabalho em branco.
1. Na guia **Inserir**, selecione **Meus suplementos**.
1. No painel direito, selecione o link **Adicionar informações do servidor**.
1. Insira a URL do servidor e selecione **OK**.
1. Se você receber uma mensagem de erro "Nenhum registro applet encontrado", siga estas etapas para resolver o problema:

    1. No Commerce, acesse **Administração do sistema \> Configuração \> Parâmetros do aplicativo Office**.
    1. Na FastTab **Parâmetros do aplicativo**, selecione **Inicializar parâmetros do aplicativo**.
    1. Na caixa de mensagem de confirmação, selecione **OK**.
    1. Na FastTab **Applets registrados**, selecione **Inicializar registro de applet**.
    1. Repita as três etapas anteriores conforme necessário.

1. Selecione **Design** e, em seguida, selecione **Adicionar tabela**.
1. Com base nos dados que devem ser modificados, selecione as entidades que devem ser adicionadas à pasta de trabalho do Excel para edição. Use a tabela a seguir como referência.

    | Tipo de transação | Entidades de dados a serem usadas |
    |------------------|----------------------|
    | Transações cash and carry, ordens online, ordens de clientes assíncronas, cotações de clientes assíncronas | Transações (auditáveis), Transações de vendas (auditáveis), Transações de pagamento (auditáveis), Transações de imposto (auditáveis), Transações de desconto (auditáveis), Transações de encargos (auditáveis) |
    | Depósito bancário | Transações (auditáveis), Transações de meio de pagamento bancário (auditáveis) |
    | Depósito no cofre | Transações (auditáveis), Transações de meio de pagamento do cofre (auditáveis) |
    | Declaração de meios de pagamento | Transações (auditáveis), Transações de declaração de meios de pagamento (auditáveis) |
    | Receita, Despesa | Transações (auditáveis), Transações de Receitas/Despesas (auditáveis), Transações de pagamento (auditáveis) |
    | Declarar valor inicial, Remoção de meio de pagamento, Entrada de flutuação, Meio de pagamento de troco, Pagamento de fatura, Depósito do cliente | Transações (auditáveis), Transações de pagamento (auditáveis) |

    > [!NOTE]
    > É importante que você adicione somente uma entidade de dados a cada pasta de trabalho do Excel. Além disso, todos os campos marcados por um símbolo de chave devem ser adicionados à pasta de trabalho relevante.

1. Depois que a pasta de trabalho estiver configurada, aplique os filtros necessários. Certifique-se de aplicar os mesmos filtros a todas as planilhas do arquivo. Evite carregar quantidades muito grandes de dados no arquivo Excel. Caso contrário, o desempenho pode ser afetado, e o Excel e seu sistema podem ficar lentos. Recomendamos que você use sempre "Empresa" e o "Número do Demonstrativo" ou o "Número da Transação" como filtros para seu arquivo.
1. Depois que os filtros forem configurados, selecione **Atualizar** para carregar os dados.
1. Edite os dados necessários e publique-os. Se o botão **Publicar** não estiver disponível, alguns campos-chave provavelmente não foram adicionados à pasta de trabalho do Excel.

## <a name="additional-resources"></a>Recursos adicionais

[Editar e auditar transações cash and carry e de gerenciamento de caixa](edit-cash-trans.md)

[Editar e auditar transações da ordem online e assíncronas da ordem do cliente](edit-order-trans.md)

[Editar dimensões financeiras para transações de varejo](edit-financial-dim.md)

[Adicionar campos a uma pasta de trabalho do Excel para editar transações de varejo](add-fields-excel.md)