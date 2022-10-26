---
title: Regras de mapeamento de solução Invoice capture
description: Este artigo fornece informações sobre a configuração das regras de mapeamento na solução Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: cd0d06f7fd3ed946756e975d0706687c2d4acc93
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691129"
---
# <a name="invoice-capture-solution-mapping-rules"></a>Regras de mapeamento de solução Invoice capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

As regras de mapeamento trazem dados mestre básicos do Microsoft Dynamics 365 Finance ou do sistema de planejamento de recursos empresariais (ERP). Depois que as regras de mapeamento são configuradas, as informações necessárias para criar faturas do fornecedor no Finance são obtidas. Quando as regras de mapeamento são usadas, o auxiliar de Contas a Pagar (AP) verificará o status em vez de preencher manualmente todos os valores de campo ausentes.

Existem quatro tipos de regras de mapeamento:

- Entidade legal
- Conta de fornecedor
- Item
- Tipo de despesa

## <a name="manage-mapping-rules-by-using-the-app"></a>Gerenciar regras de mapeamento usando o aplicativo

Para gerenciar regras de mapeamento usando o aplicativo, selecione **Configuração**. A guia **Configuração da regra de mapeamento** oferece quatro opções:

- Entidade legal 
- Conta de fornecedor 
- Mapeamento do item 
- Tipo de despesa

Por exemplo, selecione a opção **Regras de mapeamento da entidade legal**. O código da entidade legal será identificado usando o nome da empresa, o endereço e o número de registro do imposto. Para uma regra chamada **Le-USPM**, se o nome da empresa contiver o texto "Contoso Robotics USA", o código da entidade legal será **USPM**.

A página mostra todas as regras de mapeamento ativas. Se quiser exibir as regras de mapeamento inativas, selecione **Regras ativas da entidade legal de mapeamento** e selecione **Regras inativas da entidade legal de mapeamento**.

As ações a seguir estão disponíveis para regras de mapeamento.

### <a name="create-a-mapping-rule"></a>Criar uma regra de mapeamento

Você pode usar dois métodos para criar uma regra de mapeamento:

- Selecione **Nova** para criar uma nova regra de mapeamento. Em seguida, insira as informações para a regra de mapeamento. O valor **Nome da Regra** deve ser exclusivo para cada tipo de regra de mapeamento.
- Se você selecionar uma regra de mapeamento existente, o botão **Copiar** ficará disponível. Selecione-a, depois escolha **OK** na caixa de diálogo que é exibida. Uma regra de mapeamento é criada com a duplicação da regra selecionada.

### <a name="edit-a-mapping-rule"></a>Editar uma regra de mapeamento

Para editar uma regra de mapeamento, selecione um campo e altere o valor.

### <a name="activatedeactivate-mapping-rules"></a>Ativar/desativar regras de mapeamento

Para desativar uma ou mais regras de mapeamento, selecione-as na página **Regras ativas de mapeamento** e selecione **Desativar**. As regras são movidas da página **Regras ativas de mapeamento** para a página **Regras inativas de mapeamento**.

Da mesma forma, para ativar regras de mapeamento, selecione-as na página **Regras inativas de mapeamento** e selecione **Ativar**.

### <a name="remove-mapping-rules"></a>Remover regras de mapeamento

Para remover regras de mapeamento, selecione-as e escolha **Excluir**.

### <a name="check-for-conflicts"></a>Verificar conflitos

Se duas regras de mapeamento tiverem os mesmos valores de **Entidade Legal** e **Conta de Fornecedor**, mas valores de **Nome de Item** diferente, um conflito será detectado e a regra de mapeamento não será criada ou atualizada.

## <a name="importexport-mapping-rules-from-excel"></a>Importar/exportar regras de mapeamento do Excel

Um suplemento do Excel pode ser usado para gerenciar regras em um lote. As opções a seguir estão disponíveis:

- Baixar um modelo do Excel.
- Exportar para o Excel.
- Importar do Excel.

### <a name="download-an-excel-template"></a>Baixar um modelo do Excel

Para baixar um modelo do Excel, selecione **Baixar modelo**. Em seguida, selecione os campos para incluir no modelo.

### <a name="export-to-excel"></a>Exportar para Excel

Você pode exportar de duas maneiras:

- Selecione **Abrir no Excel Online** para abrir o arquivo no Excel. Você pode editar o arquivo online. Quando terminar, selecione **Salvar**. Todas as alterações serão salvas na página **Regra de mapeamento**.
- Selecione **Baixar planilha** para baixar um arquivo do Excel que contém regras de mapeamento. Em seguida, você pode editar o arquivo. Quando terminar, selecione **Importar do Excel** para carregar a planilha atualizada.

### <a name="import-from-excel"></a>Importar do Excel

1. Selecione **Importar do Excel** para importar dados de um arquivo XLSX. Você também pode importar de valores separados por vírgulas (CSV) ou arquivos XML. Antes de importar, você deve decidir se são permitidas duplicatas.
2. Selecione **Revisar Mapeamento** para revisar o mapeamento de atributos e determinar se ele está correto. Você pode modificar o relacionamento de mapeamento.
3. Quando terminar, selecione **Finalizar Importação** para iniciar a importar.
4. Você pode selecionar **Rastrear Processo** para rastrear o progresso do processo de importação.

    O status de importação é atualizado de **Finalizar** para **Analisando**, em seguida, para **Transformando**, e finalmente para **Concluído**.

Quando o processo de importação é concluído, as estatísticas de sucessos, falhas parciais, erros e totais processados são mostradas.
