---
title: Configurar faturamento de projeto intercompanhia
description: Este tópico mostra como configurar o faturamento de projeto entre duas empresas na sua organização.
author: KimANelson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, InterCompanyTradingRelationSetupVendor, SysDataAreaSelectLookup, ProjParameters, ProjPosting, ProjTransferPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c89b17c09a4f145b5a4ca9cdd127b4e635447d4b
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867310"
---
# <a name="configure-intercompany-project-invoicing"></a>Configurar faturamento de projeto intercompanhia

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este tópico mostra como configurar o faturamento de projeto entre duas empresas na sua organização. Essa tarefa usa o conjunto de dados de USSI.

1. No Painel de Navegação, vá para **Módulos > Contas a pagar > Fornecedores > Todos os fornecedores**.
2. Na lista **Todos os fornecedores**, localize e selecione o registro desejado.
3. No Painel de Ação, selecione **Geral**.
4. Selecione **Intercompanhia**.
5. Defina **Ativa** como **Sim** para habilitar comercial intercompanhia.
6. No campo **Empresa do cliente**, insira ou selecione um valor.
7. No campo **Minha conta**, insira ou selecione um valor.
8. Selecione **Salvar**.
9. Feche as páginas para voltar à home page.
10. No Painel de Navegação, vá para **Módulos > Gerenciamento e contabilidade do projeto > Configuração > Parâmetros de gerenciamento e contabilidade de projetos**.
11. Selecione a guia **Intercompanhia**.
12. Mova o controle deslizante para **Sim** para habilitar folhas de ponto e agendamento de recursos intercompanhia.
13. Na lista, marque a linha selecionada.
14. Selecione **Novo**.
15. No campo **Entidade legal que toma o empréstimo**, informe ou selecione um valor.
16. Marque a caixa de seleção **Acumular receita**.
17. No campo **Categoria de folha de ponto padrão**, insira ou selecione um valor.
18. No campo **Categoria de despesa padrão**, insira ou selecione um valor.
19. Selecione **Salvar**.
20. Feche a página.
21. No Painel de Navegação, vá para **Módulos > Gerenciamento e contabilidade do projeto > Configuração > Lançamento > Configuração de lançamento contábil**.
22. No campo **Tipos de conta contábil**, selecione uma opção.
23. Selecione **Novo**.
24. No campo **Conta principal** da nova linha, especifique os valores desejados.
25. Selecione **Salvar**.
26. Feche a página.
27. No Painel de Navegação, vá para **Módulos > Gerenciamento e contabilidade do projeto > Configuração > Preços > Preço de transferência**.
28. Selecione **Novo**.
29. No campo **Data efetiva**, insira uma data.
30. No campo **Entidade legal que toma o empréstimo**, informe ou selecione um valor.
31. No campo **Modelo de preço de transferência**, selecione uma opção.
32. No campo **Definição de preços**, insira um número.
33. Selecione **Salvar**.

