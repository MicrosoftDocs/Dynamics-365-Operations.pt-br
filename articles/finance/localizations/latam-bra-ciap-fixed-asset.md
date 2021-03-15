---
title: Adquirir e alienar um ativo fixo do CIAP
description: Os livros fiscais podem adquirir e alienar ativos fixos de ICMS recuperável a longo prazo.
author: v-gonode
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: e65f0c3daa3e4350680f8f505dacfa33b088ca19
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005780"
---
# <a name="acquire-and-dispose-a-ciap-fixed-asset"></a>Adquirir e alienar um ativo fixo do CIAP

[!include [banner](../includes/banner.md)]

## <a name="acquire-a-ciap-fixed-asset"></a>​Adquirir um ativo fixo CIAP​
Use esta funcionalidade para registrar no módulo Livros fiscais a aquisição de um ativo fixo controlado pelo ICMS recuperável a longo prazo.

1. Na página **Todas as ordens de compra**, no campo **Conta de fornecedor**, selecione um fornecedor.
2. Clique em **Adicionar linha**.
   -  Preencha os campos **Número de item**, **CFOP**, **Quantidade**, **Preço unitário**.
3. Expanda a seção Detalhes da linha.
4. Clique na guia **Ativos fixos**.
5. Selecione o campo **Sim para o novo ativo fixo?**.
6. No campo **Grupo de ativo fixo**, selecione um grupo de ativo fixo.
7. Na guia **Dimensões financeiras**, preencha os campos **CostCenter** e **Filial**.
8. Clique em **Confirmar**.
9. Na página **Todas as ordens de compra**, clique no link para selecionar uma Ordem de compra.
10. No Painel de Ação, clique em **Fatura** > **Padrão de: Quantidade de recebimento de produtos**. No campo **Quantidade padrão para linhas**, selecione uma quantidade.
11. Clique em **OK**.
12. Preencha os campos **Modelo de documento**, **Chave de acesso**, **Data da fatura** e **Data de lançamento**.
13. Clique em **Enviar**.
14. Na página **Período de escrituração**, clique em **Criar novo período de escrituração**.
15. Preencha os campos **Estabelecimento fiscal**, **Mês** e **Ano**.
16. Clique em **OK**.
17. Clique em **Sincronizar** > **OK**.
18. Clique em **ICMS** > **Apuração de imposto ICMS** > **OK**.
19. Na página **Todos os ativos fixos CIAP**, clique no link para selecionar uma ID de ativo CIAP.
20. Expanda a seção Detalhes da linha.
21. Na página **Relatório CIAP**, no campo **Estabelecimento fiscal**, insira um estabelecimento fiscal.
22. Clique em **OK**.

## <a name="dispose-of-a-ciap-fixed-asset"></a>Alienação de um ativo fixo CIAP
Use esta funcionalidade para registrar no módulo Livros fiscais a alienação de um ativo fixo controlado pelo ICMS recuperável a longo prazo.

1.  Na página **Todas as faturas de texto livre**, clique em **Novo**.
2.  Preencha os campos **ID do estabelecimento fiscal**, **Conta do cliente**, **Data**, **Descrição**, **Conta principal**, **CFOP**, **Grupo de impostos**, **Grupo de impostos do item**, **Quantidade** e **Preço unitário**.
3.  Expanda a seção **Detalhes da linha**, > no campo **Número do ativo fixo**, e insira um ativo fixo.
4.  Clique em **Enviar**.
5.  Expanda a seção **Conhecimento de embarque**, preencha os campos **Nome da transportadora**, **Tipo de volume**, **Quantidade de volume**, **Peso líquido** e **Peso bruto**.
6.  Clique em **OK**.
7.  No **Exportar/importar processo de NF-e** > **OK**.
8.  Na página **Período de escrituração** > **Criar novo período de escrituração**.
9.  Preencha os campos **Estabelecimento fiscal**, **Mês** e **Ano**.
10. Clique em **OK**.
11. Clique em **Sincronizar** > **OK**.
12. Clique em **ICMS** > **Apuração de imposto ICMS** > **OK**.
13. Na página **Todos os ativos fixos CIAP**, clique no link para selecionar uma ID de ativo CIAP.
14. No **Relatório CIAP**, no campo **Estabelecimento fiscal**, selecione um estabelecimento fiscal.
15. Clique em **OK**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]