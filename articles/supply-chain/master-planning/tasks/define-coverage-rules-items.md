---
title: Definir regras de cobertura para itens
description: Este procedimento mostra como criar regras de cobertura e substituir configurações de cobertura para um item específico. Também mostra como especificar as configurações padrão de estoque.
author: ChristianRytt
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3947c8a51facfb02012cc8e9a3ffd5887073bd9
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2021
ms.locfileid: "7860604"
---
# <a name="define-coverage-rules-for-items"></a>Definir regras de cobertura para itens

[!include [banner](../../includes/banner.md)]

A empresa de dados demo usada para criar este procedimento é USMF. Este procedimento mostra como criar regras de cobertura e substituir configurações de cobertura para um item específico. Também mostra como especificar as configurações padrão de estoque.

## <a name="create-a-coverage-group"></a>Crie um grupo de cobertura.

Crie um grupo de cobertura da seguinte maneira:

1. Acesse **Painel de navegação > Módulos > Planejamento mestre > Configuração > Grupos de cobertura**.
1. Selecione **Novo**.
1. No campo **Grupo de cobertura**, digite um valor.
1. No campo **Nome**, digite um valor.
1. No campo **Calendário**, digite um valor. Escolha o calendário utilizado pelo planejamento mestre para criar indicações de reabastecimento para itens desse grupo.  
1. No campo **Código de cobertura**, selecione uma opção. Selecione 'Requisito' para este procedimento.  
1. No campo **Limite de tempo de cobertura (dias)**, insira '90'. Para itens desse grupo, o planejamento mestre criará indicações de reabastecimento por até 90 dias no futuro.  
1. No campo **Dias negativos**, insira '1'.
1. No campo **Dias positivos**, insira '1'.
1. Expanda ou recolha a seção **Outros**.
1. Na seção **Margens de segurança em dias**, no campo **Margem de recebimento adicionada à data de requisição**, insira '1'. Por exemplo, se a margem de recebimento estiver definida para 1 dia, e uma linha da ordem de compra estiver programada para recebimento em 15 de maio, o planejamento mestre calculará a data de recebimento ajustada como 16 de maio.
1. No campo **Margem de emissão deduzida da data de requisição**, insira '1'. Por exemplo, se a margem de segurança estiver definida como 1 dia, e uma linha da ordem de venda estiver programada para entrega em 15 de maio, o agendamento do planejamento mestre calculará a data de entrega ajustada como 14 de maio.  
1. No campo **Reordenar margem adicionada ao prazo de entrega do item**, insira '1'.
1. Selecione **Salvar**.

## <a name="create-a-new-product"></a>Criar um novo produto

Crie um produto da seguinte maneira:

1. Acesse **Painel de Navegação > Módulos > Gerenciamento de informações do produto > Produtos > Produtos liberados**.
1. Selecione **Novo**.
1. No campo **Número do produto**, digite um valor.
1. No campo **Nome do produto**, digite um valor.
1. No campo **Grupo de modelos do item**, selecione o botão suspenso para abrir a pesquisa.
1. Na lista, localize e selecione o registro desejado.
1. Na lista, selecione o link na linha selecionada.
1. No campo **Grupo de itens**, selecione o botão suspenso para abrir a pesquisa.
1. Na lista, localize e selecione o registro desejado.
1. Na lista, selecione o link na linha selecionada.
1. No campo **Grupo de dimensões de armazenamento**, selecione o botão suspenso para abrir a pesquisa.
1. Na lista, localize e selecione o registro desejado.
1. Na lista, selecione o link na linha selecionada.
1. No campo **Grupo de dimensões de rastreamento**, selecione o botão suspenso para abrir a pesquisa.
1. Na lista, localize e selecione o registro desejado.
1. Na lista, selecione o link na linha selecionada.
1. Selecione **OK**.

## <a name="set-up-default-order-settings"></a>Definir configurações padrão da ordem

Defina as configurações padrão da ordem da seguinte maneira:

1. No **Painel de Ações**, selecione **Plano**.
1. Em **Configurações da ordem**, selecione **Configurações padrão da ordem**.
1. Em **Ordem de compra**, no campo **Site padrão**, digite o site usado como padrão quando ordens de compra são criadas.
1. No campo **Depósito padrão**, digite o local onde o item está armazenado.
1. Expanda ou recolha a seção **Estoque**.
1. No campo **Múltiplo**, digite '10'.
1. No campo **Quantidade mínima para ordem**, digite '10'.
1. No campo **Quantidade máxima para ordem**, digite '100'.
1. No campo **Quantidade da ordem padrão**, digite '10'.
1. No campo **Prazo de entrega da compra**, insira um número.
1. Marque ou desmarque a caixa de seleção **Dias úteis**.
1. Selecione **Salvar**.
1. No campo **Tipo de ordem padrão**, selecione 'Ordem de compra'.
1. Selecione **Salvar**.
1. Feche a página. Feche a página Configurações padrão da ordem.  

## <a name="add-an-item-to-a-coverage-group"></a>Adicionar um item ao grupo de cobertura

Adicione um tem a um grupo de cobertura da seguinte maneira:

1. Expanda ou recolha a seção **Plano**.
1. No campo **Grupo de cobertura**, selecione o botão suspenso para abrir a pesquisa.
1. Na lista, localize o **Grupo de cobertura** que você criou.
1. Na lista, selecione o link na linha selecionada.

## <a name="create-item-coverage-rules"></a>Criar Regras de cobertura de item

Crie regras de cobertura de item da seguinte maneira:

1. No **Painel de Ações**, selecione **Plano**.
1. Em **Cobertura**, selecione **Cobertura de item**.
1. Selecione **Novo**.
1. Selecione a guia **Geral**.
1. Marque a caixa no cabeçalho de **Substituir configurações do grupo de cobertura**.
1. No campo **Limite de tempo de cobertura (dias)**, insira '60'. Embora os itens no grupo de cobertura Requiremen sejam planejados 90 dias depois, esse item será planejado com 60 dias.  
1. No campo **Dias negativos**, insira '2'.
1. No campo **Dias positivos**, insira '2'.
1. Selecione a guia **Prazo de entrega**.
1. Marque a caixa no cabeçalho de **Compra**.
1. No campo **Tempo de compra**, insira '5'.
1. Selecione **Salvar**.

> [!NOTE]
> Para itens fabricados, o **Prazo de entrega da produção** será usado se não houver um roteiro para o item. Se um roteiro ativo tiver sido associado ao item, o planejamento mestre agendará o pedido e calculará as datas de acordo com o tempo do roteiro e a capacidade dos recursos (se aplicável).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
