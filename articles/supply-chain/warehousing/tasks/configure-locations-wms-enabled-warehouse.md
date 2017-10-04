--- 
title: "Configurar localizações em um depósito habilitado para WMS"
description: "Este guia mostra como definir a configuração da localização para um novo depósito habilitado para WMS (um depósito que utiliza processos avançados de gerenciamento de depósito)."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 044da854273345877be92c9eab787f4edf0bba5b
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="configure-locations-in-a-wms-enabled-warehouse"></a>Configurar localizações em um depósito habilitado para WMS

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este guia mostra como definir a configuração da localização para um novo depósito habilitado para WMS (um depósito que utiliza processos avançados de gerenciamento de depósito). O processo é normalmente feito por um gerente de depósito. Você pode executar esse guia na empresa de dados demonstrativos USMF ou usando seus próprios dados. Uma pré-condição é que você tenha pelo menos um local configurado.


## <a name="create-a-new-warehouse"></a>Criar um novo depósito
1. Vá para Depósitos.
2. Clique em Novo.
3. No campo Depósito, digite um valor.
4. No campo Nome, digite um valor.
5. No campo Local, digite um valor.
6. Expandir ou recolher a seção Depósito.
7. Defina a opção Utilize processos de gerenciamento de depósito como Sim.
    * Essa configuração permite que você execute processos de armazenamento avançados utilizando trabalho de depósito e dispositivos móveis.  
8. Feche a página.

## <a name="define-a-location-format"></a>Definir um formato de localização
1. Vá para Formatos de localização.
    * Formatos de localização são um sistema de nomeação utilizado para criar nomes únicos e consistentes para as diferentes localizações dos compartimentos usados dentro de um depósito. Pode ser útil usar separadores como parte do formato do local para facilitar a identificação dos componentes do local tal como o número do corredor. Neste exemplo, iremos criar um nome com quatro componentes. Por exemplo, eles podem ser corredor, estante, prateleira e compartimento.  
2. Clique em Novo.
3. No campo Formato de localização, digite um valor.
4. No campo Nome, digite um valor.
5. No campo Descrição do segmento, digite um valor.
    * Isso descreve o que o primeiro componente do nome da localização representa. Por exemplo, poderia ser Corredor.  
6. No campo Comprimento, insira um número.
    * Isso determinará quantos caracteres essa parte do nome da localização deve ter. Observe que o total de todos os componentes do nome, incluindo os separadores, não pode exceder 10 caracteres.  
7. No campo Separador, digite um valor.
    * Isso determina qual caractere ou símbolo é usado entre o primeiro e o segundo componente do nome.  
8. Clique em Novo.
9. No campo Descrição do segmento, digite um valor.
10. No campo Comprimento, insira um número.
11. No campo Separador, digite um valor.
12. Clique em Novo.
13. No campo Descrição do segmento, digite um valor.
14. No campo Comprimento, insira um número.
15. No campo Separador, digite um valor.
16. Clique em Novo.
17. No campo Descrição do segmento, digite um valor.
18. No campo Comprimento, insira um número.
19. Clique em Salvar.
20. Feche a página.

## <a name="define-location-types"></a>Definir tipos de localizações
1. Vá para Tipos de localização.
    * Os tipos de localização podem ser utilizados como opções de filtragem para controlar os diferentes processos de gerenciamento de depósito. No mínimo, você precisa criar os tipos de localização processamento e despacho final para definir o processo de gerenciamento de saída do depósito.  
2. Clique em Novo.
3. No campo Tipo de localização, digite um valor.
4. No campo Descrição, digite um valor.
5. Feche a página.

## <a name="define-location-profile"></a>Definir perfil de localização
1. Vá para Perfis de localização.
    * A definição de perfis de localização é muito importante. A capacidade de localizações agrupadas pode ser controlada aqui, assim como as políticas relacionadas a qual estoque é armazenado, e como é armazenado. Perfis de localização podem ser utilizadas como opções de filtragem para controlar os diferentes processos de gerenciamento do depósito. No mínimo, você deve criar um perfil de localização do usuário para habilitar os processos de gerenciamento do depósito.  
2. Clique em Novo.
3. No campo ID do perfil de localização, digite um valor.
4. No campo Nome, digite um valor.
5. No campo Formato da localização, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o registro desejado.
7. Na lista, clique no link na linha selecionada.
8. No campo Tipo de localização, clique no botão suspenso para abrir a pesquisa.
9. Na lista, localize e selecione o PDV desejado.
10. Na lista, clique no link na linha selecionada.
11. Marque ou desmarque a caixa de seleção Permitir status de estoque mistos.
    * Habilite esta opção se desejar permitir valores mistos de status de estoque nas localizações que serão agrupadas por esse perfil de localização.  
12. Marque ou desmarque a caixa de seleção Substituir regras para dias de lote.
    * Habilite esta opção para substituir a regra que diz respeito à quantidade de dias que as datas de vencimento de lote de estoque podem divergir, para permitir a mistura de lotes de estoque que não obedecem essa regra.  
13. Marque ou desmarque a caixa de seleção Permitir contagem cíclica.
    * Habilite esta opção para permitir o processo de contagem cíclica em todas as localizações que serão agrupadas por esse perfil de localização.  
14. Expandir ou recolher a seção Dimensões.
    * A aba Dimensões permite que você defina parâmetros e métodos para habilitar cálculos precisos da capacidade de carga dentro de cada localização.  
15. Feche a página.

## <a name="enable-warehouse-management-parameters"></a>Habilitar parâmetros de gerenciamento do depósito
1. Vá para Parâmetros de gerenciamento de depósito.
    * Para que seja possível processar o trabalho de depósito, você precisa definir parâmetros para o perfil de localização do usuário, o tipo da localização de preparo, e o tipo da localização do despacho final. Assim que o processo de saída terminar no tipo da localização de despacho final definido, as transações de saída relacionadas serão atualizadas para 'Retirado'.  
2. Expandir ou recolher a seção Perfis de localização.
3. No campo Localização de usuário, clique no botão suspenso para abrir a pesquisa.
4. Na lista, clique no link na linha selecionada.
5. Expandir ou recolher a seção Tipos de locais.
6. No campo Tipo de localização de preparo, clique no botão suspenso para abrir a pesquisa.
7. Na lista, clique no link na linha selecionada.
8. No campo Tipo de localização de despacho final, clique no botão suspenso para abrir a pesquisa.
9. Na lista, clique no link na linha selecionada.
10. Feche a página.

## <a name="define-warehouse-zone-groups"></a>Definir grupos de zonas de depósito
1. Vá para Grupos de zonas do depósito.
    * Zonas de depósito podem ser utilizadas como filtros para opções de controle dos diferentes processos de gerenciamento do depósito. Você deve criar um grupo de zonas para que seja possível definir uma zona.  
2. Clique em Novo.
3. No campo ID do grupo de zonas, digite um valor.
4. No campo Nome do grupo de zonas, digite um valor.
5. Feche a página.

## <a name="define-warehouse-zones"></a>Definir Zonas de depósito
1. Vá para Zonas.
2. Clique em Novo.
3. No campo ID de zona, digite um valor.
4. No campo Nome da zona, digite um valor.
5. No campo ID do grupo de zonas, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o registro desejado.
7. Na lista, clique no link na linha selecionada.
8. Feche a página.

## <a name="create-locations-using-the-location-setup-wizard"></a>Criar localizações utilizando o Assistente de configuração de localização
1. Vá para Assistente de configuração de localização.
2. No campo Depósito, clique no botão suspenso para abrir a pesquisa.
3. Na lista, localize e selecione o registro desejado.
4. Na lista, clique no link na linha selecionada.
5. No campo ID de zona, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o registro desejado.
7. Na lista, clique no link na linha selecionada.
8. No campo ID do perfil de localização, clique no botão suspenso para abrir a pesquisa.
9. Na lista, localize e selecione o registro desejado.
10. Na lista, clique no link na linha selecionada.
11. Na lista, marque a linha selecionada.
12. No campo Do número, insira um número.
    * Os campos Do número e Até o número definem quantas localizações serão criadas. Por exemplo, se você definir Do número para 1 e Até o número para 3 em todas as quatro linhas do formato de localização, 81 localizações serão criadas (3x3x3x3).  
13. No campo Até o número, insira um número.
14. Na lista, localize e selecione o PDV desejado.
15. No campo Do número, insira um número.
16. No campo Até o número, insira um número.
17. Na lista, localize e selecione o registro desejado.
18. No campo Do número, insira um número.
19. No campo Até o número, insira um número.
20. Na lista, localize e selecione o registro desejado.
21. No campo Do número, insira um número.
22. No campo Até o número, insira um número.
23. Clique em Criar.

## <a name="create-locations-manually"></a>Criar localizações manualmente
1. Vá para Localizações.
    * A criação manual de localizações dentro de um depósito pode ser facilmente realizada. O nome da localização e o ID do perfil de localização são valores obrigatórios.  
2. Clique em Novo.
3. No campo Depósito, digite um valor.
4. No campo Localização, digite um valor.
    * Observe que você está criando uma nova localização aqui, então você precisa digitar um novo nome exclusivo, em vez de selecionar um existente.  
5. No campo ID do perfil de localização, digite um valor.
6. Feche a página.

## <a name="define-pack-size-categories"></a>Definir Categorias de tamanho do pacote
1. Vá para Categorias de tamanho do pacote.
    * As categorias de tamanho do pacote podem ser utilizadas para agrupar itens que possuem tamanhos físicos de embalagem semelhantes. Neste exemplo a categoria de tamanho do pacote será usada para controlar a capacidade nos locais de retirada dentro de uma zona específica do depósito. Por favor observe que o ID da categoria de tamanho do pacote deve ser atribuído à entidade do produto lançado para que possa ser usado como parte do processamento dos limites de armazenamento.  
2. Clique em Novo.
3. No campo ID de categoria de tamanho do pacote, digite um valor.
4. No campo Nome da categoria de tamanho do pacote, digite um valor.
5. Feche a página.

## <a name="define-location-stocking-limits"></a>Definir limites de estoque de localização
1. Vá para Limites de armazenamento da localização.
    * Os limites de armazenamento do local ajudam a garantir que não será criado trabalho para solicitar que o estoque seja colocado em uma localização que não possui a capacidade física necessária para suportá-lo.  
2. Clique em Novo.
3. No campo Depósito, digite um valor.
4. No campo ID do perfil de localização, digite um valor.
5. No campo ID de categoria de tamanho do pacote, digite um valor.
6. No campo Quantidade, insira um número.
7. Clique em Salvar.
8. Feche a página.

## <a name="define-fixed-picking-locations"></a>Definir locais de retirada fixos
1. Vá para Localizações fixas.
    * Você pode definir as localizações a serem utilizadas por produto ou por variante do produto. É possível criar várias localizações fixas para o mesmo produto dentro do mesmo depósito.  
2. Clique em Novo.
3. No campo Número de item, digite um valor.
4. No campo Depósito, digite um valor.
5. No campo Localização, clique no botão suspenso para abrir a pesquisa.
6. Na lista, clique no link na linha selecionada.
7. Feche a página.

