---
title: Criar uma ordem de compra repetida
description: Este artigo mostra como criar uma ordem de compra (PO) da repetição copiando linhas de um documento de ordem mais adiantado da compra a uma PO nova ou a uma PO existente.
author: GalynaFedorova
ms.date: 09/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, PurchCopying
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 335461d60fa0bc92e9711806c6e42643a3f75d02
ms.sourcegitcommit: 073604c07116e0a87f78ab2c76cb89ae83ebba3c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9608097"
---
# <a name="create-a-repeat-purchase-order"></a>Criar uma ordem de compra repetida

[!include [banner](../../includes/banner.md)]

Este artigo mostra como criar uma ordem de compra (PO) da repetição copiando linhas de um documento de ordem mais adiantado da compra a uma PO nova ou a uma PO existente. Há dois métodos para criar ordens da repetição. Você pode usar as ações disponíveis a nível do documento da placa da ação, ou você pode usar a linha de ações do detalhe. As ações do nível do documento estão voltadas principalmente à criação de uma ordem de compra adicionando linhas e informações de cabeçalho de uma outra ordem, quando a ação dos detalhes da linha for principalmente a adição de linhas a uma ordem existente. O exemplo mostrado neste guia pode ser usado na empresa dos dados do programa demonstrativo de USMF. Normalmente essa tarefa é realizada por um agente de compras.

## <a name="create-a-new-repeat-purchase-order"></a>Criar uma nova ordem de devolução

1. No painel de navegação, acesse **Módulos \> Compras e Fornecimento \> Ordens de compra \> Todas as ordens de compra**. Primeiramente nós tentaremos a opção para copiar informação de uma ordem nova.  
1. Selecione **Novo**.
1. No campo **Conta de fornecedor**, insira `US-101`.
1. Selecione **OK**.
1. No Painel de ações, abra a guia **Ordem de compra** e, no grupo **Copiar**, selecione **De todos**. A caixa de diálogo **Copiar de outros documentos** será aberta. Daqui, você poderá copiar de ordens de compra existentes para sua ordem. Há opções diferentes para como as linhas são copiadas, e uns tipos diferentes dos documentos de que você pode copiar. Nós olharemos as opções para como as linhas são copiadas primeiramente.
1. Expanda a Guia Rápida **Parâmetros**.

    - O campo **Fator de quantidade** é útil se você precisa usar uma quantidade que seja diferente do que essa que está na ordem da qual você está copiando. Por exemplo, se você quer pedir duas vezes a quantidade que está nas linhas que você está copiando, você insere "2" neste campo e então o sistema adicionará as linhas onde a quantidade original foi dobrada.  
    - O **Reverter sinal** também muda a quantidade pedida mudando o sinal da quantidade para as linhas da ordem que são adicionadas. Isto pode ser útil se você precisa inverter uma transação, criando as linhas da ordem que negam a transação. Esta opção é selecionada automaticamente quando a página é aberta da ação **Criar nota de crédito**.  
    - A opção **Copiar encargos** permite que você copie cargas a sua ordem nova do documento que você está copiando das linhas da ordem.  
    - A opção **Recalcular preços** usa os preços atuais e os descontos em vez de copiar estes do documento que você está copiando da outra informação.  
    - A opção **Copiar exatamente** copia os valores de vários campos no cabeçalho e nas linhas da ordem. Se esta opção não for selecionada, os valores padrão serão usados para muitos dos campos relacionados ao fornecedor e aos produtos, da mesma maneira que como se você estivesse criando a ordem manualmente. Por exemplo, se definir **Copiar exatamente** como *Sim* e copiar a ordem que substitui a conta de fatura padrão do fornecedor, a mesma conta da fatura seria copiada para a nova ordem. Se definir **Copiar exatamente** como *Não*, a conta de fatura padrão do fornecedor será usada na nova ordem. Os valores para os campos a seguir são copiados quando a opção **Copiar exatamente** é definida como *Sim*:
        - Idioma
        - Condições de pagamento
        - Método de pagamento
        - Especificação de pagamento
        - Grupo de sequências numéricas
        - Desconto à vista
        - Percentual de desconto
        - Moeda
        - Condições de entrega
        - Modo de entrega
        - Dimensão
        - Grupo de impostos sobre vendas
        - Substituir imposto
        - Preços incluem imposto
        - Transporte
        - Porta
        - Procedimento estatístico
        - ID do Modelo
        - Nome para entrega
        - Endereço postal
        - Demonstrativo
        - ID da tabela de referência
    - A opção **Excluir linhas de compra** exclui todas as linhas da ordem de compra que já existem na ordem de compra que você está copiando, antes de aplicar as novas linhas. Use esta opção com cuidado, pois ela suprime todas as linhas existentes sem aviso adicional.  
    - Se você usa a opção **Cabeçalho da ordem de cópia**, você não precisa criar manualmente a informação de cabeçalho em sua ordem nova. Esta opção fará com que os valores padrão sejam usados para os campos associados com o fornecedor. Se o documento que você está copiando tem os valores do sem-padrão que você quer copiar, use também a opção **Copiar exatamente**.
    - Há fontes de documento diferentes que você pode copiar, e cada uma tem uma seção separada nesta página. Por exemplo, a seção **Ordens de compra** permite que você copie as ordens de compra existentes.  

1. Na seção **Ordens de compra**, selecione as linhas que deseja copiar na área de transferência. É possível selecionar linhas adicionais das ordens de compra de outras ordens de compra e copiá-las também a sua ordem. É igualmente possível adicionar linhas de outros tipos de documentos da compra. As próximas etapas reveem as opções diferentes.  
1. Expanda a seção **Confirmação**. Aqui você pode selecionar confirmações da ordem de compra para copiar. As confirmações da ordem de compra são identificadas pela identificação associada do diário de compras ou pela identificação da ordem de compra.  
1. Expanda a seção **Recebimento de produtos**. Aqui você pode selecionar diários de recebimento de produtos para copiar. Os jornais do recibo do produto são identificados pelo comprovante do recibo do produto ou pela identificação da ordem de compra.
1. Expanda a seção **Faturas**. Aqui você pode selecionar faturas de fornecedor para copiar. As faturas são identificadas pelo comprovante da fatura ou pela identificação da ordem de compra.
1. Expanda a seção **Linhas ou cabeçalho selecionados para cópia**. Esta exibição mostra um sumário de todos os documentos e as linhas que você selecionou para serem copiados a sua ordem.
1. Selecione **OK**. As linhas que você selecionou foi copiada agora a sua nova ordem de compra.

## <a name="copy-lines-to-an-existing-purchase-order"></a>Copie linhas a uma ordem de compra existente  

Em vez de copiar uma ordem inteira, é mais comum criar uma PO nova e uma informação completa no cabeçalho da PO, e copia então linhas individuais das ordens existentes.  

1. Selecione uma **Linha de ordem de compra**.
1. Selecione **De tudo**. A página que abre é idêntica a essa mostrada antes, mas as opções diferentes são selecionadas quando abre as linhas vista da ordem. Vamos revisar os parâmetros.
1. Expanda a seção **Parâmetros**.

    - A opção **Excluir linhas de compra** não é selecionada. Isto significa que você pode copiar novas linhas a sua ordem sem remover as linhas existentes.
    - A opção **Copiar cabeçalho da ordem** também não é selecionada, porque estamos adicionando somente linhas adicionais à ordem.
    - Para este exemplo, nós copiaremos linhas de uma ordem de compra existente.

1. Selecione a linha da ordem de compra desejada. Observe que a única linha da ordem que está nesta PO também está selecionada.  
1. Selecione **OK**. A linha adicional da ordem foi adicionada a sua ordem de compra.  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]