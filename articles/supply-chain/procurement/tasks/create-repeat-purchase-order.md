---
title: Criar uma ordem de compra repetida
description: Este tópico mostra como criar uma ordem de compra (PO) da repetição copiando linhas de um documento de ordem mais adiantado da compra a uma PO nova ou a uma PO existente.
author: mkirknel
manager: tfehr
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, PurchCopying
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9bf5e92ad6bc62dd008a51aacca891cb7253a723
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422534"
---
# <a name="create-a-repeat-purchase-order"></a>Criar uma ordem de compra repetida

[!include [banner](../../includes/banner.md)]

Este tópico mostra como criar uma ordem de compra (PO) da repetição copiando linhas de um documento de ordem mais adiantado da compra a uma PO nova ou a uma PO existente. Há dois métodos para criar ordens da repetição. Você pode usar as ações disponíveis a nível do documento da placa da ação, ou você pode usar a linha de ações do detalhe. As ações do nível do documento estão pretendidas principalmente ao criar uma ordem de compra adicionando linhas e informação de cabeçalho de uma outra ordem, quando a linha de ação dos detalhes for principalmente adicionando linhas a uma ordem existente. O exemplo mostrado neste guia pode ser usado na empresa dos dados do programa demonstrativo de USMF. Normalmente essa tarefa é realizada por um agente de compras.


## <a name="create-a-new-repeat-purchase-order"></a>Criar uma nova ordem de devolução
1. No painel de navegação, vá para **Módulos > Compras e fornecimento > Ordens de compra > Todas as ordens de compra**. Primeiramente nós tentaremos a opção para copiar informação de uma ordem nova.  
2. Selecione **Novo**.
3. No campo **Conta de fornecedor**, insira `US-101`.
4. Selecione **OK**.
5. No Painel de Ações, selecione **Ordem de compra**.
6. Selecione **De tudo**. Esta é a página da qual você pode copiar as ordens existentes a sua ordem. Há opções diferentes para como as linhas são copiadas, e uns tipos diferentes dos documentos de que você pode copiar. Nós olharemos as opções para como as linhas são copiadas primeiramente. 
7. Expanda a seção **Parâmetros**.

    - O campo **Fator de quantidade** é útil se você precisa usar uma quantidade que seja diferente do que essa que está na ordem da qual você está copiando. Por exemplo, se você quer pedir duas vezes a quantidade que está nas linhas que você está copiando, você insere "2" neste campo e então o sistema adicionará as linhas onde a quantidade original foi dobrada.  
    - O **Reverter sinal** também muda a quantidade pedida mudando o sinal da quantidade para as linhas da ordem que são adicionadas. Isto pode ser útil se você precisa inverter uma transação, criando as linhas da ordem que negam a transação. Esta opção é selecionada automaticamente quando a página é aberta da ação **Criar nota de crédito**.  
    - A opção **Copiar encargos** permite que você copie cargas a sua ordem nova do documento que você está copiando das linhas da ordem.  
    - A opção **Recalcular preços** usa os preços atuais e os descontos em vez de copiar estes do documento que você está copiando da outra informação.  
    - A opção **Copiar exatamente** cria uma cópia exata dos valores em todos os campos no cabeçalho e nas linhas do documento de ordem. Se esta opção não for selecionada, os valores padrão são usados para muitos dos campos em relação ao vendedor e aos produtos apenas como se você estivesse criando a ordem nova manualmente. Por exemplo, se a ordem que você está copiando substituiu a conta de fatura padrão do fornecedor, a mesma conta da fatura seria copiada para sua ordem. Se você não selecionou a opção **Copiar exatamente**, a conta de fatura padrão para o fornecedor seria usada em sua ordem, em vez disso.  
    - A opção **Excluir linhas de compra** exclui todas as linhas da ordem de compra que já existem na ordem de compra que você está copiando, antes de aplicar as novas linhas. Use esta opção com cuidado, pois ela suprime todas as linhas existentes sem aviso adicional.  
    - Se você usa a opção **Cabeçalho da ordem de cópia**, você não precisa criar manualmente a informação de cabeçalho em sua ordem nova. Note que esta opção conduzirá aos valores padrão que estão sendo usados para os campos associados com o vendedor. Se o documento que você está copiando tem os valores do sem-padrão que você quer copiar, use também a opção **Copiar exatamente**.   
    - Há fontes de documento diferentes que você pode copiar, e cada uma tem uma seção separada nesta página. Por exemplo, a seção **Ordens de compra** permite que você copie as ordens de compra existentes.  

8. Na seção **Ordens de compra**, selecione as linhas que deseja copiar na área de transferência. É possível selecionar linhas adicionais das ordens de compra de outras ordens de compra e copiá-las também a sua ordem. É igualmente possível adicionar linhas de outros tipos de documentos da compra. As próximas etapas reveem as opções diferentes.  
9. Expanda a seção **Confirmação**. Aqui você pode selecionar confirmações da ordem de compra para copiar. As confirmações da ordem de compra são identificadas pela identificação associada do diário de compras ou pela identificação da ordem de compra.  
10. Expanda a seção **Recebimento de produtos**. Aqui você pode selecionar diários de recebimento de produtos para copiar. Os jornais do recibo do produto são identificados pelo comprovante do recibo do produto ou pela identificação da ordem de compra.   
11. Expanda a seção **Faturas**. Aqui você pode selecionar faturas de fornecedor para copiar. As faturas são identificadas pelo comprovante da fatura ou pela identificação da ordem de compra.   
12. Expanda a seção **Linhas ou cabeçalho selecionados para cópia**. Esta exibição mostra um sumário de todos os documentos e as linhas que você selecionou para serem copiados a sua ordem.   
13. Selecione **OK**. As linhas que você selecionou foi copiada agora a sua nova ordem de compra.   

## <a name="copy-lines-to-an-existing-purchase-order"></a>Copie linhas a uma ordem de compra existente  

Em vez de copiar uma ordem inteira, é mais comum criar uma PO nova e uma informação completa no cabeçalho da PO, e copia então linhas individuais das ordens existentes.  

1. Selecione uma **Linha de ordem de compra**.
2. Selecione **De tudo**. A página que abre é idêntica a essa mostrada antes, mas as opções diferentes são selecionadas quando abre as linhas vista da ordem. Vamos revisar os parâmetros.   
3. Expanda a seção **Parâmetros**.

    - A opção **Excluir linhas de compra** não está selecionada. Isto significa que você pode copiar novas linhas a sua ordem sem remover as linhas existentes.   
    - A opção **Copiar cabeçalho da ordem** também não é selecionada, porque estamos adicionando somente linhas adicionais à ordem.   
    - Para este exemplo, nós copiaremos linhas de uma ordem de compra existente.   

4. Selecione a linha da ordem de compra desejada. Observe que a única linha da ordem que está nesta PO também está selecionada.  
5. Selecione **OK**. A linha adicional da ordem foi adicionada a sua ordem de compra.  

