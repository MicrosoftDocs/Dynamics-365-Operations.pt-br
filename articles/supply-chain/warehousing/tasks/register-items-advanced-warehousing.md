---
title: Registrar itens para um item avançado com armazenamento habilitado usando um diário de entrada de itens
description: Este procedimento mostra como registrar itens usando o diário de entrada de itens quando estiver usando processos de gerenciamento de depósito avançado.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c25fb55afb01ed59b66045f24400e03e2ec60b2a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238885"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a>Registrar itens para um item avançado com armazenamento habilitado usando um diário de entrada de itens

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como registrar itens usando o diário de entrada de itens quando estiver usando processos de gerenciamento de depósito avançado. Normalmente isso é feito por um vendedor de remessa. 

Você pode executar esse procedimento na empresa de dados demonstrativos USMF, ou usando seus próprios dados. Você precisa ter uma ordem de compra confirmada com uma linha de ordem de compra aberta antes de dar início a este guia. O item da linha deve ser armazenado, e não deve usar grades de produto, e não deve ter dimensões de rastreamento. E o item precisa estar associado a um grupo de dimensões de armazenamento habilitado para processo de gerenciamento de depósito. O depósito usado deve ser habilitado para processos de gerenciamento de depósito, e a localização usada para recebimento deve ser controlada por placa de licença. Se estiver utilizando USMF, você pode usar a conta da companhia 1001, depósito 51 e item M9200 para criar sua OC. 

Juntamente com o número da ordem de compra criada, anote o número do item e o site que você usou para sua linha de ordem de compra.


## <a name="create-an-item-arrival-journal-header"></a>Criar um cabeçalho de diário de entrada de itens.
1. Vá para Entrada de item.
2. Clique em Novo.
3. No campo Nome, digite um valor.
    * Se você estiver usando USMF, você pode digitar WHS. Se você estiver usando outros dados, o diário cujo nome que você escolheu precisa ter as seguintes propriedades: O local de separação de verificação deve ser definido como nenhum, e o gerenciamento de quarentena deve ser definido como não.  
4. No campo Número, digite um valor.
5. No campo Local, digite um valor.
    * Selecione o site que você usou para sua ordem de compra aqui. Isso servirá como um valor padrão para todas as linhas do diário. Se você usou o depósito 51 na USMF, selecione o site 5.  
6. No campo Depósito, digite um valor.
    * Selecione um depósito válido para o site que você selecionou. Isso servirá como um valor padrão para todas as linhas do diário. Se você estiver usando os valores do exemplo na USMF, selecione 51.  
7. No campo Localização, digite um valor.
    * Selecione uma localização válida no depósito que você selecionou. A localização precisa estar associada a um perfil de localização, o que é controlado por placa de licença. Isso servirá como um valor padrão para todas as linhas do diário. Se você estiver usando os valores do exemplo na USMF, selecione Bulk-008.  
8. Clique com o botão direito do mouse na seta suspensa no campo Placa de licença e selecione Exibir detalhes.
9. Clique em Novo.
10. No campo Placa de licença, digite um valor.
    * Anote o valor.  
11. Clique em Salvar.
12. Feche a página.
13. No campo Placa de licença, digite um valor.
    * Insira o valor da placa de licença que acabou de criar. Isso servirá como um valor padrão para todas as linhas do diário.  
14. Clique em OK.

## <a name="add-a-line"></a>Adicionar uma linha
1. Clique em Adicionar linha.
2. No campo Número de item, digite um valor.
    * Insira o número do item que usou na linha da ordem de compra.  
3. No campo Quantidade, insira um número.
    * Insira a quantidade que deseja registrar.  
    * O campo Data determina a data na qual a quantidade disponível desse item será registrada no estoque.  
    * O ID do lote será preenchido pelo sistema se puder ser identificado somente nas informações fornecidas. Caso contrário, você terá que adicioná-lo manualmente. Trata-se de um campo obrigatório, que vincula esse registro a uma linha de documento de origem específica.  

## <a name="complete-the-registration"></a>Concluir o registro
1. Clique em Validar.
    * Isso verifica se o diário está pronto para ser lançado. Se a validação falhar, você precisará corrigir os erros antes de poder lançar o diário.  
2. Clique em OK.
    * Após clicar em OK, verifique a mensagem. Deve haver uma mensagem informando que o diário está OK.  
3. Clique em Lançar.
4. Clique em OK.
    * Após clicar em OK, verifique a barra de mensagem. Deve haver uma mensagem informando que a operação foi concluída.  
5. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]