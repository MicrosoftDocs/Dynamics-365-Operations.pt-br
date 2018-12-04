--- 
title: Configurar embalagem manual (fevereiro de 2016 e maio de 2016)
description: "O processo de embalagem permite que você valide e empacote produtos em contêineres."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: b90b4a71e2447e942dbb4a9645ef93064da630d3
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-manual-packing-february-2016--may-2016"></a>Configurar embalagem manual (fevereiro de 2016 e maio de 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

O processo de embalagem permite que você valide e empacote produtos em contêineres. Nesse processo, os trabalhadores do depósito escolhem produtos dos locais de depósito e os movem para uma estação de embalagem onde eles podem verificar as quantidades e tipos, e atribuí-los aos contêineres apropriados. Quando um contêiner é embalado totalmente, poderá fechá-lo e movê-lo para as docas de saída, e o produto está pronto para ser enviado. Este procedimento usa a empresa de dados de demonstração USMF. Este procedimento é somente para as versões de fevereiro de 2016 e de maio de 2016 do Dynamics 365 for Operations.


## <a name="set-up-location-profiles"></a>Configurar perfis de localização
1. Vá para Gerenciamento de depósito > Configuração > Depósito > Perfis de localização.
2. Clique em Novo.
    * O perfil de local é usado para estações de embalagem e contém informações e as regras para um local.  
3. No campo ID do perfil de localização, digite um valor.
4. No campo Nome, digite um valor.
5. No campo Formato de local, insira ou selecione um valor.
6. No campo Tipo de local, insira ou selecione um valor.
7. Selecione Sim no campo Permitir itens misturados.
8. Selecione Sim no campo Permitir status de estoque misturados.
9. Selecione Sim nas Regras de substituição para o campo de dias do lote.
10. Feche a página.

## <a name="set-up-warehouse-management-parameters"></a>Configurar parâmetros para gerenciamento de depósito 
1. Vá para Gerenciamento de depósito > Configuração > Parâmetros de gerenciamento de depósito.
2. Clique na guia Pacote.
3. No campo ID de perfil para local de pacote, insira ou selecione um valor.
    * Selecione o perfil de local que deseja usar para separação.  
4. Feche a página.

## <a name="set-up-container-types"></a>Configure tipos de contêiner
1. Vá para Gerenciamento de depósito > Configuração > Recipientes > Tipos de recipiente.
2. Clique em Novo.
    * É possível definir os tipos de contêineres a serem usados. Você pode especificar as dimensões físicas do contêiner, incluindo o peso de tara, o peso máximo, o volume máximo, o tamanho, a largura, e o peso.  Os Atributos são campos personalizáveis que permitem adicionar dimensões extra no tipo de contêiner.     
3. No campo Código de tipo de contêiner, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Tara, insira um número.
6. No campo Peso máximo, insira um número.
7. No campo Volume, insira um número.
8. No campo Comprimento, insira um número.
9. No campo Largura, insira um número.
10. No campo Altura, insira um número.
11. Clique em Salvar.
12. Feche a página.

## <a name="set-up-packing-profiles"></a>Configurar perfis de embalagem
1. Vá para Gerenciamento de depósito > Configuração > Empacotamento > Perfis de empacotamento.
2. Clique em Novo.
3. No campo ID de perfil de pacote, insira um valor.
4. No campo Descrição, digite um valor.
5. No campo ID de perfil de fechamento de Contêiner, insira ou selecione um valor.
    * A identificação do perfil do fechamento do contêiner é opcional e é o novo perfil padrão do contêiner para o perfil de embalagem.  
6. No campo Modo de ID de contêiner, selecione uma opção.
    * Esta opção determina se uma ID de contêiner será gerada automaticamente quando um contêiner é criado ou se uma ID de contêiner será criado manualmente.  
7. No campo Tipo de contêiner, insira ou selecione um valor.
    * O tipo de contêiner será usado por padrão quando um novo contêiner é criado.  
8. Selecione a caixa de seleção Criar automaticamente contêiner no fechamento do contêiner.
9. Clique em Salvar.
10. Feche a página.

## <a name="set-up-container-closing-profiles"></a>Configurar perfis de fechamento de contêiner
1. Vá para Gerenciamento de depósito > Configuração > Recipientes > Perfis de fechamento de recipientes.
    * Os perfis de fechamento de contêiner definem o que acontece quando um contêiner é fechado. Você pode configurar perfis de contêiner múltiplos próximos.       
2. Clique em Novo.
3. No campo ID de perfil de fechamento de Contêiner, insira um valor.
4. No campo Descrição, digite um valor.
5. No campo Manifestar em, selecione uma opção.
    * Especifique se a manifestação ocorrerá ao fechar os contêineres ou ao confirmar a remessa. Observe que a manifestação requer o gerenciamento de transporte. A manifestação deve ser implementada nos mecanismos de transporte para que ela funcione.  
6. No campo Depósito, insira ou selecione um valor.
7. No campo Local padrão para envio final, insira ou selecione um valor.
    * Esse será o local para o qual os produtos serão movidos depois que os contêineres são fechados. Esta localização deve ter um perfil de local definido nos Parâmetros de depósito.  
8. No campo Unidade de peso, insira ou selecione um valor.
9. Clique em Salvar.


