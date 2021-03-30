---
title: Gerenciar arrendamentos por meio da estrutura de importação de arrendamento
description: Este tópico explica como usar a Estrutura de importação de arrendamento para ajustar vários arrendamentos ao mesmo tempo.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 90727e8624c8edb7cd9458089dd9d6dfaad67a7f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207222"
---
# <a name="manage-leases-through-the-lease-import-framework"></a>Gerenciar arrendamentos por meio da estrutura de importação de arrendamento

[!include [banner](../includes/banner.md)]

Este tópico explica como usar a Estrutura de importação de arrendamento para ajustar vários arrendamentos em uma etapa. Ao usar esse recurso, você poderá poupar tempo e também garantir ajustes mais precisos, reduzindo a probabilidade de erro humano. Além disso, esse recurso pode conectar o Microsoft Dynamics 365 Finance a entidades de dados externas para carregar dados com eficiência.

As seguintes entidades de dados podem ser usadas para integrar o Arrendamento de ativos a sistemas externos:

- Preparo de arrendamento
- Preparo de contrato de pagamento
- Preparo de contrato de execução

Você pode usar o processo de importação para ajustar um arrendamento, atualizar informações não financeiras ou adicionar novos arrendamentos. Você pode exibir e editar os dados de leasing antes de importá-los.

O sistema pode executar os três processos a seguir por meio do pacote de importação de arrendamento.

| Tipo de processo  | descrição |
|---------------|-------------|
| Adicionar registro    | Os arrendamentos migrados com esse tipo de processo criam um arrendamento no sistema. O plano de pagamento deve ser confirmado manualmente e a entrada do diário de reconhecimento inicial deve ser lançada manualmente após a migração. |
| Atualizar registro | Os arrendamentos migrados com esse tipo de processo atualizam valores de campo para um arrendamento que já está no sistema. Somente os campos selecionados na página **Atualizar seleção de campos** são atualizados. É recomendável selecionar campos não financeiros na página **Atualizar seleção de campos**, pois esse tipo de processo não ajusta o arrendamento. |
| Ajustar registro | Os arrendamentos migrados com esse tipo de processo ajustam o arrendamento. Esse ajuste causa uma modificação no arrendamento mercantil do arrendamento. Após o processamento do arrendamento, o sistema cria uma nova agenda de pagamento usando os novos dados do pacote de importação de arrendamento. O sistema não confirma a agenda de pagamento ou o lançamento da entrada do diário de ajuste. |

Depois que as informações forem carregadas por meio do espaço de trabalho **Gerenciamento de dados**, abra a página **Importar cabeçalho** (**Arrendamento de ativos \> Estrutura de importação de arrendamento \> Importar cabeçalho**). Esta página lista todas as importações das três entidades de dados listadas anteriormente.

Para exibir os dados de preparo de arrendamento antes da execução do processamento, selecione **Dados de preparo**.

A função comparar permite comparar um registro que está sendo importado com o registro correspondente que já está no sistema. Para comparar um registro de arrendamento individual, selecione um arrendamento e depois **Comparar**. Você deve concluir esta etapa para gerar um relatório **Diferenças** antes de migrar os registros de arrendamento. A funcionalidade Comparar compara os valores dos dados de preparo com os valores para os arrendamentos que estão no sistema no momento.

> [!NOTE]
> A funcionalidade Comparar não funciona para arrendamentos com o tipo de processo **Adicionar registro**, porque não há nada para comparar ao arrendamento.
>
> Para comparar vários arrendamentos ao mesmo tempo, acesse **Arrendamento de ativos \> Estrutura de importação de arrendamento \> Periódico \> Comparar** e selecione **Comparar**.

Para cada entidade, você pode exibir as diferenças entre o que está atualmente no sistema e o que está nas tabelas de preparo. Para cada entidade nas tabelas de preparo, selecione **Consultar diferenças**. A caixa de diálogo exibida mostra o valor atual e o valor de preparo proposto.

Você também pode atualizar o valor de preparo alterando-o na coluna **Novo Valor** e selecionando **Atualizar preparo**.

Você pode validar arrendamentos para garantir que os registros possam ser trazidos para o sistema sem introduzir erros. Antes da migração de um registro de arrendamento, o sistema executa várias validações para garantir que o registro seja importado com êxito. Para validar um arrendamento individual, selecione **Validar**.

> [!NOTE]
> Para validar vários arrendamentos ao mesmo tempo, acesse **Arrendamento de ativos \> Estrutura de importação de arrendamento \> Periódico \> Validar** e selecione **Comparar**.

Para processar um arrendamento individual, selecione **Migrar registros de arrendamento** na página **Importar cabeçalho**. Quando um arrendamento é migrado, o sistema executa a ação especificada no campo **Tipo de processo**.

> [!NOTE]
> Para validar vários arrendamentos ao mesmo tempo, acesse **Arrendamento de ativos \> Estrutura de importação de arrendamento \> Periódico \> Validar** e selecione **Comparar**.

Após a comparação dos arrendamentos, você poderá executar um relatório para exibir as diferenças para cada arrendamento incluído na ID de importação. Para executar o relatório para um arrendamento, selecione o arrendamento nos dados de preparo e selecione **Comparar e exibir relatório \> Relatório de diferenças**.

> [!NOTE]
> Para validar vários arrendamentos ao mesmo tempo, acesse **Arrendamento de ativos \> Consultas e relatórios \> Relatório de diferenças** e selecione **Comparar**.

## <a name="set-up-update-fields"></a>Configurar campos de atualização

Se estiver usando a estrutura de importação de arrendamento para atualizar arrendamentos e o tipo de processo for **Atualizar registro**, você poderá selecionar campos específicos para atualizar.

1. Acesse **Arrendamento de ativos \> Estrutura de importação de arrendamento \> Configuração \> Atualização de seleção de campo**.
2. Na página exibida, selecione os campos a serem atualizados e, em seguida, selecione a seta verde para movê-los para a lista **Campos selecionados**. Somente os campos na lista de **Campos selecionados** podem ser atualizados com o uso do pacote de importação de arrendamento.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]