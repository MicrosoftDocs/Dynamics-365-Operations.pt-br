--- 
title: "Criar um novo layout de depósito"
description: "Este procedimento mostra como configurar informações sobre as localizações de um depósito."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 15610bc797cf7e7abdec433d0a5cead60da7a555
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-new-warehouse-layout"></a>Criar um novo layout de depósito

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como configurar informações sobre as localizações de um depósito. Aplica-se apenas a depósitos criados usando o "armazenamento básico” no módulo de gerenciamento de estoque, não a depósitos criados no módulo de gerenciamento de depósito. Você pode usar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.


## <a name="set-the-default-location-capacity"></a>Definir a capacidade do local padrão
1. Vá para Gerenciamento de estoque > Configuração > Parâmetros de gerenciamento de depósito e estoque.
2. Clique na guia Locais.
3. No campo de largura padrão, insira um número.
4. No campo de profundidade padrão, insira um número.
5. No campo de altura padrão, insira um número.
6. Clique em Salvar.
7. Feche a página.

## <a name="define-the-location-name-format"></a>Definir o formato do nome da localização
1. Vá para Gerenciamento do estoque > Configuração > Divisão do estoque > Depósitos.
2. Clique em Novo.
3. No campo Depósito, digite um valor.
4. No campo Nome, digite um valor.
5. No campo Local, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o PDV desejado.
7. Alternar a expansão da seção Nomes de local.
    * As opções nesta seção definem o formato padrão para nomes da localização. Em nosso exemplo, incluiremos o número do corredor, o número do rack e o número da prateleira.  
8. Definir a opção do corredor para Sim.
9. Definir a opção do rack para Sim. 
10. No campo Formato, digite o valor para o rack.
    * Por exemplo: -##  
11. Definir a opção Incluir prateleira como Sim.
12. No campo Formato, digite o valor para a prateleira.
    * Por exemplo: -##  

## <a name="define-warehouse-locations"></a>Definir locais de depósito
1. No Painel de Ação, clique em Depósito.
2. Clique em Assistente de localização.
3. Clique em Avançar.
4. Desmarque a opção de Docas de saída
5. Desmarque a opção de Locais de massa
6. Clique em Avançar.
7. Clique em Avançar.
8. Clique em Avançar.
9. Clique em Avançar.
10. Clique em Avançar.
11. Clique em Avançar.
12. Clique em Avançar.
    * Observe que as dimensões físicas mostradas nessa página são aquelas configuradas que você definiu no início deste procedimento.  
13. Clique em Avançar.
14. Clique em Finish (Concluir).
15. Feche a página.
16. Atualize a página.


