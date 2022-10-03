---
title: Permitir edições em dados internos em comprovantes de contabilidade
description: Este artigo fornece informações sobre como editar dados internos em comprovantes da contabilidade.
author: kweekley
ms.date: 08/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 6e346c6ff881d3a33743196b45247493fd19ed1d
ms.sourcegitcommit: adadbc6e355e2ad68a1f6af26a1be1f89dc8eec6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573242"
---
# <a name="allow-edits-to-internal-data-on-general-ledger-vouchers"></a>Permitir edições em dados internos em comprovantes de contabilidade

[!include[banner](../includes/banner.md)]


Quando você lança entradas contábeis na contabilidade, o campo **Descrição** costuma ser usado para armazenar anotações internas ou documentação. Se as informações estiverem incorretas, isso poderá gerar confusão e dificultar o fechamento do período de finalização. Esse recurso permite que o gerente ou o supervisor de contabilidade corrija erros editando o campo **Descrição** em comprovantes lançados na contabilidade.

As alterações em comprovantes lançados na contabilidade são limitadas a dados internos por natureza. Esse recurso nunca permitirá que você edite dados como valores, datas de lançamento, contas contábeis e a moeda da transação. As alterações feitas nos dados afetarão o relatório externo de demonstrativos financeiros e devem ser feitas somente por meio de comprovantes da contabilidade.

> [!NOTE]
> No Dynamics 365 Finance versão 10.0.29, este recurso está limitado a edições no campo **Descrição**.

## <a name="edit-internal-data-on-general-ledger-vouchers"></a>Editar dados internos em comprovantes de contabilidade

Para que os dados internos em comprovantes da contabilidade possam ser editados, você deve habilitar o recurso **Permitir edições em dados internos em comprovantes de contabilidade** no espaço de trabalho **Gerenciamento de recursos**.
Depois que o recurso for habilitado, o usuário que editar comprovantes lançados deverá ter a função de gerente ou supervisor contábil atribuída a ele. Também é possível adicionar permissões a outras funções, personalizando os direitos de acesso.

O processo de edição só é permitido na página Transações de comprovante.

1. Vá para **Contabilidade** > **Consultas e relatórios** > **Transações de comprovante**.
2. Na caixa de diálogo **SysQuery**, insira critérios de pesquisa para selecionar comprovantes.
3. Selecione as linhas dos comprovantes que deseja editar e, depois, **Editar comprovante** > **Editar dados de comprovante interno**.

    [![Página Comprovantes de transações.](./media/voucher-transactions-page.png)](./media/voucher-transactions-page.png)
    
Na página **Editar dados de comprovante interno**, os seguintes dados são exibidos para cada linha selecionada:
  
  - Conta contábil
  - Nome da conta
  - Comprovante
  - Descrição atual
  - Nova descrição

    [![Comprovante de diário.](./media/edit-internal-voucher-data.png)](./media/edit-internal-voucher-data.png)
    
> [!NOTE]
> Só é possível editar o campo **Nova descrição**. Por padrão, o valor corresponde ao valor do campo **Descrição atual**, permitindo que você corrija erros pequenos na descrição.

4. Modifique o campo **Nova descrição** em cada linha ou exclua a descrição de cada linha.

   Como alternativa, se várias linhas precisarem ser atualizadas com o mesmo valor, siga estas etapas:

      1. Selecione as linhas a serem editadas e, depois, **Atualização em massa dos registros selecionados**.
      2. Em **Campo a ser editado**, selecione o campo a ser editado. No momento, a pesquisa inclui somente o campo **Nova descrição**.
      3. No campo **Novo valor**, insira uma nova descrição.
      4. Selecione **Atualizar**. Todos os registros selecionados são atualizados com o novo valor.

      [![Caixa de diálogo Atualização em massa dos registros selecionados.](./media/bulk-update-selected-records.png)](./media/bulk-update-selected-records.png)
    
5. No campo **Motivo da edição**, insira uma nota para explicar por que a edição foi feita. Esta nota é mostrada na página **Trilha de auditoria de edições de comprovante**.

   É possível fazer várias edições no mesmo comprovante, e cada edição será rastreada.

## <a name="audit-trail-of-voucher-edits"></a>Trilha de auditoria de edições de comprovante

Uma trilha de auditoria é mantida especificamente para rastrear as alterações feitas por meio desse recurso. É possível acessar a trilha de auditoria das edições de comprovantes de duas formas:

  - Vá para **Contabilidade** > **Consultas e relatórios** > **Transações de comprovante**. Na página **Consultas de comprovante**, selecione **Editar comprovante** > **Trilha de auditoria de edições de comprovante**. A trilha de auditoria é mostrada somente para o registro de comprovante selecionado. 
   
    Ao abrir a consulta dessa forma, você pode se concentrar em todas as edições que foram feitas em um único registro de comprovante.
  
  - Vá para **Contabilidade geral** > **Tarefas periódicas** > **Trilha de auditoria de edições de comprovante**. Na caixa de diálogo, insira critérios para especificar os comprovantes para os quais você deseja exibir a trilha de auditoria de edições. Para exibir a trilha de auditoria para todos os comprovantes, deixe os critérios em branco e selecione **OK**. 
    
    Ao abrir a consulta dessa forma, você pode filtrar por edições feitas em uma data específica ou por um usuário específico.

A página **Trilha de auditoria de edições de comprovante** mostra as seguintes informações:

- **Data e hora de criação**: a data e a hora da edição.
- **Motivo da edição**: o motivo que o usuário inseriu para a edição.
- **Criado por**: o usuário que fez a edição.

Para exibir os detalhes de cada trilha de auditoria, faça uma busca detalhada do valor **Data e hora de criação**. A página **Exibir propriedades do comprovante editado** mostra as mesmas informações que a página Editar original, incluindo a descrição anterior e a descrição atualizada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
