---
title: Configurar destinos ER
description: Este procedimento demonstra como configurar e usar os diferentes componentes de saída para eletrônicos (ER), como uma pasta ou um arquivo.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERFormatDestinationTable, SysLookupPicklist, ERFormatDestinationSettings, ERFormatDestinationEmailSettings, ERExpressionDesignerFormula, SRSPrintDestinationTokens
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f1e679b52b28ff1ca117c5224fc7e2825feb26e5e5aea1c8b5bc3a88d1eaf235
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6743254"
---
# <a name="er-configure-destinations"></a>Configurar destinos ER

[!include [banner](../../includes/banner.md)]

Este procedimento demonstra como configurar e usar os diferentes componentes de saída para eletrônicos (ER), como uma pasta ou um arquivo. A empresa de dados demonstrativos utilizada para criar esse procedimento é a DEMF. Alemanha é o país/região de endereço principal da entidade legal; porém, você pode usar todas as entidade legais para este procedimento. 

O formato usado nesse exemplo é a transferência de crédito ISO20022, mas você pode usar qualquer formato que você já importou. Observe que esse procedimento é um exemplo de uma configuração de arquivo e de destino únicos. Mais informações sobre o Gerenciamento do destino de relatório eletrônico podem ser encontradas na ajuda do Dynamics 365 Finance.

1. Acesse Administração da organização > Relatório eletrônico > Destino de relatório eletrônico.
2. Clique em Novo para criar um novo conjunto de metas para um formato.
3. No campo Referência, selecione um formato para o qual você deseja definir os alvos.
    * Se você não tiver um valor para selecionar, significa que não importou qualquer configuração eletrônica no formato do relatório. Você deve importar uma configuração de formato antes de configurar destinos.  
4. Clique em Novo para criar um novo destino de arquivo.
    * Observe que você pode criar um destino de arquivo para cada componente de saída do mesmo formato, como uma pasta ou um arquivo. Você pode habilitar ou desabilitar separadamente destinos nas configurações.  
5. No campo Nome, digite um nome fácil de usar de componente de saída.
    * É recomendável usar nomes significativos, como "Arquivo de pagamento" ou "Relatório de controle". Esses nomes serão apresentadas para usuários em tempo de execução de configuração juntamente com as configurações de destino.  
6. No Nome do arquivo, selecione um arquivo ou pasta que é específico ao formato.
7. Clique em Configurações.
8. Selecione Sim no campo Habilitado.
    * A caixa de seleção habilitada em todas as guias habilita ou desabilita cada meta separadamente. Neste exemplo, você habilitará enviar um arquivo de saída para um destinatário de email quando o arquivo for gerado.  
9. Clique em Editar, para configurar destinatários do email.
10. Clique em Adicionar.
11. Clique em Imprimir email de gerenciamento.
12. No campo Origem de email, selecione uma opção.
    * Você pode selecionar diferentes tipos de origem de email, como um cliente ou um tipo de fornecedor. Isso define o tipo de argumento que será retornado pela fórmula da conta de origem de email. A fórmula da conta de origem de email, descrita em uma etapa seguinte, é o local onde você associará uma origem de email. Selecione Fornecedor se a fórmula retornará uma conta de fornecedor. Use Fornecedor se estiver usando o exemplo de configuração de transferência de crédito ISO 20022.  
13. Clique no botão Associação de origem de email.
14. Em Fórmula, digite uma referência específica a um tipo de participante que você selecionou anteriormente.
    * Em vez de digitar, você pode encontrar um nó da fonte de dados que representa a conta do participante e clicar no botão Adicionar fonte de dados para atualizar a fórmula. Por exemplo, se você usar a configuração da transferência de crédito ISO 20022, o nó que representa uma conta de fornecedor é '$PaymentsForCoveringLetter'.Creditor.Identification.SourceID. Caso contrário, insira qualquer valor da cadeia de caracteres, como "DE-001", para salvar a fórmula.  
15. Clique em Salvar.
16. Feche a página.
17. Clique em Editar para configurar os detalhes de contato do participante.
18. Selecione Sim no campo Contato principal.
    * Você pode usar diferentes opções para indicar qual tipo de contato do participante deve ser usado como endereço de email para esse destino. Usamos o contato principal nesse exemplo.  
19. Clique em OK.
20. Clique em OK.
21. No campo Assunto, digite um valor.
22. Clique em OK.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]