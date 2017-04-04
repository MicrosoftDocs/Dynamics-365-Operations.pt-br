---
title: "O cliente faz a visão geral"
description: "Este tópico fornece informações sobre ordens de cliente no retail moderno POS (MPOS). Ordens do cliente também são conhecidos como encomendas especiais. O tópico inclui uma auditoria de parâmetros relacionados a transação e fluxos."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 2f466dfe53ccf0be15ed0793b4a6dd371bdacc0d
ms.lasthandoff: 03/31/2017


---

# <a name="customer-orders-overview"></a>O cliente faz a visão geral

Este tópico fornece informações sobre ordens de cliente no retail moderno POS (MPOS). Ordens do cliente também são conhecidos como encomendas especiais. O tópico inclui uma auditoria de parâmetros relacionados a transação e fluxos.

Em um mundo de varejo de omni- canal, vários fornecedores oferecem a opção de ordens do cliente, ou de encomendas, e atender a várias necessidades de produto e de orçamento. Eis alguns típicos cenários:

-   Um cliente deseja os produtos a ser entregue a um endereço específico em uma data específica.
-   Um cliente deseja pegarar produto de uma loja ou de um local diferente do armazenamento ou do local onde o cliente adquiriu esses produtos.
-   Um cliente desejar alguém pessoa para pegarar os produtos do cliente fez compras.

Os fornecedores também use ordens de cliente minimizar vendas perdidas que as interrupções de em estoque podem causar de outra forma, pois a mercadoria pode ser entregue ou pegarado em horários ou local diferente.

## <a name="set-up-customer-orders"></a>Ordens de instalação do cliente
Eis alguns parâmetros que podem ser definidos ** parâmetros de varejo ** na página para definir como as ordens do cliente forem atendidos:

-   ** Porcentagem de disposição padrão ** – especifique o valor que o cliente deve pagar um depósito como uma ordem antes que possa ser confirmada. O valor padrão do depósito é calculado como uma porcentagem do valor da ordem. Um segundo privilégios, associado de loja consiga substituir valor usando ** substituição ** de depósito.
-   ** O porcentagem de encargos de cancelamento ** – se um encargo será aplicado quando uma ordem de cliente é cancelado, especifique o valor do encargo.
-   ** O código de encargo de cancelamento ** – se um encargo será aplicado quando uma ordem de cliente seja cancelado, o encargo será refletido em um código de encargos na ordem de venda no Microsoft Dynamics AX. Use esse parâmetro para definir o código de encargo de cancelamento.
-   ** O código de encargo de remessa – fornecedores ** pode cobrar uma taxa adicional para enviar as mercadorias para um cliente. O valor da taxa de remessa será refletido em um código de encargos na ordem de venda no dynamics AX. Use esse parâmetro para mapear o código de encargo de remessa a taxas de remessa na ordem de cliente.
-   ** Encargos de remessa de descontos ** – especifique se as taxas de remessa que são associadas com uma ordem do cliente forem reembolsáveis.
-   ** O valor máximo aprovação sem ** – se as taxas de remessa são reembolsáveis, especifique o valor máximo dos descontos de encargo de remessa por meio de ordens de devolução. Se esse valor for excedido, a substituição gerente é necessária para continuar com o desconto. Para acomodar os seguintes cenários, um reembolso taxas de remessa pode ultrapassar o valor que foi originalmente pago:
    -   Os encargos são aplicados no cabeçalho de ordem de venda e, quando a quantidade de uma linha de produtos é devolvida, o desconto máximo taxas de remessa que é permitido para os bens e a quantidade não pode ser determinado na forma como trabalhar para todos os clientes de varejo.
    -   As taxas de remessa são utilizadas para cada instância de remessa. Se um cliente devolve produtos várias vezes e, a diretiva do fornecedor especifica que o fornecedor cobrar o custo de taxas de remessa de devolução, encargos de remessa de devolução forem mais das taxas de remessa.

## <a name="transaction-flow-for-customer-orders"></a>Fluxo de transação em ordens de cliente
### <a name="create-a-customer-order-in-retail-modern-pos"></a>Criar uma ordem de cliente no retail POS moderno

1.  Adicione um cliente à transação.
2.  Adicionar produtos ao carrinho.
3.  O clique ** criar ordem de cliente **, e selecione o tipo de ordem. O tipo de ordem pode ser ** ou ordem de cliente ou ** ** ** cotação.
4.  O clique ** remessa selecionado ** ou tudo ** ** enviar para enviar o produto para um endereço na conta de cliente, especifique a data de remessa solicitada, e especificar taxas de remessa.
5.  Clique ** escolher selecionado acima ou Pick-up ** ** ** para selecionar todos os produtos a serem retirados de armazenamento atual ou de um armazenamento diferente em uma data específica.
6.  Coletar o valor de depósito, se um depósito é necessário.

### <a name="edit-an-existing-customer-order"></a>Editar uma ordem existente de cliente

1.  Na página, clique em localizar ** ** uma ordem.
2.  Localize e selecione a ordem que deseja editar. Na parte inferior da página, clique ** ** edição.

### <a name="pick-up-an-order"></a>Pegare uma ordem

1.  Na página, clique em localizar ** ** uma ordem.
2.  Selecione a ordem pegarar. Na parte inferior da página, clique em separação e ** ** embalagem.
3.  Clique pegare ** **.

### <a name="cancel-an-order"></a>Cancelar uma ordem

1.  Na página, clique em localizar ** ** uma ordem.
2.  Selecione a ordem cancelar. Na parte inferior da página, clique em cancelar ** **.

#### <a name="create-a-return-order"></a>Criar uma ordem de devolução

1.  Na página, clique em localizar ** ** uma ordem.
2.  Selecione a ordem, e selecione a nota fiscal para a ordem, e selecione a linha de produtos para as mercadorias a serem devolvidos.
3.  Na parte inferior da página, clique ** devolver ** ordem.

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Fluxo assíncrona de transação em ordens de cliente
Ordens de cliente podem ser criadas de clientes (POS) da venda em modo síncrona ou em modo assíncrona.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Habilitar ordens de cliente seja criado em modo assíncrona

1.  Em O dynamics AX, clique ** varejo e comércio ** &gt; ** a configuração de canal ** &gt; ** configuração POS ** &gt; ** perfil POS ** &gt; ** ** perfis de funcionalidade.
2.  ** ** Em geral, FastTab definir ** criar ordem de cliente no modo de async ** a opção ** Sim **.

** Quando criar ordem de cliente no modo de async ** a opção seja definida ** Sim **, as ordens do cliente são sempre criadas em modo assíncrona, mesmo que o transaction service (RTS) estiver disponível. Se você definir esta opção ** nenhuma **, ordens de cliente é criado sempre em modo síncrona usando o RTS. Quando as ordens do cliente são criados em modo assíncrona, são recebidos e inseridos em O dynamics AX por remessa (P) trabalho. Ordens de venda correspondentes serão criados em O dynamics AX quando ** ordens de sincronizar ** executado manualmente ou com um processo em lote.

<a name="see-also"></a>Consulte também
--------

[] Híbridos ordens de cliente (hybrid-customer-orders.md)


