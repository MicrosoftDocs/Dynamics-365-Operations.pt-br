---
title: Criar locais funcionais
description: Este tópico explica como criar um local funcional em Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationCopyStructure, EntAssetFunctionalLocationCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1875ddd5c57639830a70aeebf7ef41114044f839
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253653"
---
# <a name="create-functional-locations"></a>Criar locais funcionais

[!include [banner](../../includes/banner.md)]

 

Este tópico explica como criar um local funcional em Gerenciamento de Ativos.

Quando você criar uma estrutura de local funcional, note que, após criar um local funcional, você não poderá movê-lo da localização original. Isso significa que é necessário considerar cuidadosamente a estrutura dos seus locais funcionais antes de iniciar a criação delas em Gerenciamento de Ativos. Se você lamenta um local funcional, pode excluí-lo, desde que ele ainda não esteja em uso.

Para poder trabalhar com locais funcionais, você começa criando duas "categorias" de locais funcionais:

- Crie *um* local funcional padrão sem sublocais. Este local funcional é usada somente como local padrão para ativos quando você cria novos ativos.  
- Crie as estruturas de local funcional obrigatórias gerenciando trabalhos de manutenção em sua empresa.

## <a name="create-a-default-functional-location"></a>Crie um local funcional padrão.

Ao utilizar locais funcionais, comece criando um local padrão a ser usado quando você criar novos ativos. Este local funcional é o que você seleciona no link **Gerenciamento de ativos** > **Configuração** > **Parâmetros de gerenciamento de ativos** > **Ativos** > campo **Local funcional padrão**. O local funcional padrão pode ser usado quando você cria novos ativos e ainda não configurou uma estrutura de local funcional para esses ativos.

1. Selecione **Gerenciamento de ativos** > **Comum** > **Locais funcionais** > **Todos os locais funcionais**.  
2. Em **Todos os locais funcionais**, selecione **Novo**.
3. Insira um ID no campo **Local funcional**; por exemplo, "0000" ou "Padrão", para indicar que este é um local funcional especial.
4. Insira um nome para o local funcional padrão no campo **Nome**.
5. *Não* selecione um pai no campo **Pai** – deixe este campo em branco.
6. No campo **Tipo de local funcional**, selecione o tipo de local funcional a ser usado para o local funcional padrão. Consulte [Tipos de locais funcionais](../setup-for-functional-locations/functional-location-types.md) para obter mais informações sobre como configurar tipos de locais funcionais.
7. Selecione **OK**. Você não deve adicionar mais dados a este local funcional pois ele será usado somente como um local temporário para novos ativos até você instalar os ativos nos locais funcionais usados pela sua empresa.

## <a name="create-functional-locations"></a>Criar locais funcionais

O procedimento a seguir descreve como você cria locais funcionais necessários para o gerenciamento de manutenção em sua empresa.

1. Selecione **Gerenciamento de ativos** > **Comum** > **Locais funcionais** > **Todos os locais funcionais**. Você pode criar um local funcional na exibição de grade ou na exibição de detalhes.
2. Selecione o botão **Novo**.
3. Insira uma ID no campo **Local funcional**.
4. Insira um nome para o local funcional no campo **Nome**.
5. Se o local funcional for um sublocal em uma estrutura, selecione o local pai no campo **Pai**.
6. Selecione um tipo no campo **Tipo de local funcional**.
7. Selecione **OK**.
8. Selecione o local funcional e clique no botão **Editar** para adicionar mais informações.

>[!NOTE]
>Dependendo da configuração dos estados do ciclo de vida do local funcional, talvez você precise criar todos os sublocais para um local funcional e, depois, modificar o estado do ciclo de vida do local funcional antes de começar a instalação de ativos. Consulte [Instalar ativos em locais funcionais](../functional-locations/install-objects-on-functional-locations.md) para obter mais informações sobre a instalação de ativos. Consulte [Estados do ciclo de vida de locais funcionais](../setup-for-functional-locations/functional-location-stages.md) para saber mais sobre a configuração dos estados do ciclo de vida de locais funcionais.

Na exibição de detalhes, você verá a Guia Rápida em que você pode adicionar e editar informações sobre o local funcional.

## <a name="general-information"></a>Informações Gerais

Esta seção fornece uma visão geral de informações pai e filho na estrutura de local funcional. Na seção **Detalhes**, você pode ver o número de atributos de ativo, planos de manutenção e ativos relacionados ao local funcional. Na seção **Estoque**, você pode selecionar o site e o depósito aos quais o local funcional está relacionado. O site e o depósito são usados em conexão com as previsões de item de ordem de serviço. Quando você cria uma previsão de itens, informações de site e depósito do local funcional do ativo são usadas automaticamente. Na seção **Estado do ciclo de vida**, aparecem informações sobre o estado do ciclo de vida do local funcional.

## <a name="installed-assets"></a>Ativos instalados

Consulte [Instalar ativos em locais funcionais](../functional-locations/install-objects-on-functional-locations.md) para obter mais informações sobre a instalação de ativos. Você pode usar o botão **Exibir** nesta Guia Rápida para exibir mais campos na Guia Rápida. Os campos **Válido a partir de** e **Subativo** podem ser exibidos na grade.

## <a name="asset-attribute-requirements"></a>Requisitos de atributos do ativo

Nesta Guia Rápida, você pode adicionar requisitos específicos de atributos para os ativos que você instala no local funcional. Esses requisitos são meramente informativos. Eles não impedem que você instale ativos com outros requisitos de atributos. Selecione **Adicionar linha** e o tipo de atributo. Após inserir o **Valor** relevante, selecione um limite no campo **Critérios de limite** e salve o registro.

## <a name="maintenance-plans-and-maintenance-rounds"></a>Planos de manutenção e rounds de manutenção

Aqui você pode adicionar planos e rounds de manutenção no local funcional, incluindo uma data inicial. Os ativos instalados em um local funcional podem ter outros planos de manutenção configurados. Todos os planos e rounds de manutenção podem ser usados para agendar entradas de calendário de ativo para um local funcional e seus ativos atualmente instalados.

>[!NOTE]
>Se você atualizar a configuração de tipos de ativos, marcas de ativos e modelos de ativos nos planos de manutenção na exibição de detalhe **Todos os locais funcionais** > Guia Rápida **Planos de manutenção** após ter agendado planos de manutenção, as entradas da agenda de manutenção existentes relacionadas a esse local funcional serão excluídas automaticamente. Para criar novas entradas da agenda, que correspondam ao plano de manutenção atualizado no local funcional, você deve executar uma nova agenda de plano de manutenção para esse local funcional. 

## <a name="address"></a>Endereço

Insira o endereço do local funcional na Guia Rápida **Endereço**. Os endereços em locais funcionais são herdados. Isso significa que, se um sublocal não tiver endereço definido, o endereço do local pai será usado.

## <a name="workers"></a>Trabalhadores

Nesta Guia Rápida, você pode adicionar trabalhadores afiliados ao local funcional e pode selecionar um local funcional como principal para o trabalhador. 

## <a name="attributes"></a>Atributos

Nesta Guia Rápida, você pode definir valores para atributos de local funcional. Esses atributos podem ser usados para descrever as propriedades ou características pertinentes ao local funcional; por exemplo, as propriedades estruturais, tipo de construção, descrições da área ou o local acima ou abaixo da terra.

Selecione **Adicionar linha** e o tipo de atributo. Em seguida, insira o **Valor** relacionado ao tipo de atributo e salve o registro.

## <a name="financial-dimensions"></a>Dimensões financeiras

Você pode selecionar dimensões financeiras para o local funcional. [Tipos de locais funcionais](../setup-for-functional-locations/functional-location-types.md) podem ser configurados para permitir a atualização automática das dimensões financeiras de um local funcional. Isso significa que os ativos instalados em uma dimensão financeira recebem automaticamente as dimensões financeiras para o local funcional. Isso será útil se você desejar centros de custo diferentes, dependendo dos locais.

Quando os dados em relação a **Site**, **Depósito**, **Endereço** e **Dimensões financeiras** são atualizados em um local funcional pai, os sublocais funcionais relacionados podem ser atualizados de acordo se você faz essa seleção durante a atualização. Uma caixa de diálogo é aberta, fornecendo as opções de atualização.

## <a name="copy-a-functional-location-structure"></a>Copie uma estrutura do local funcional

Se sua empresa tiver vários locais funcionais com estruturas de local semelhantes, você poderá usar a função de cópia em Gerenciamento de Ativos para criar rapidamente um número de hierarquias de locais semelhantes. Ao copiar um local funcional específico ou uma estrutura inteira, o novo local ou estrutura terá o mesmo nome daquele que você copiou. Após o procedimento de cópia, você pode alterar facilmente o nome ou outras configurações no novo local funcional, desde que o estado do ciclo de vida do local funcional selecionado para o novo local funcional permita isso.

1. Em **Todos os locais funcionais**, selecione o local funcional a ser copiado. Por exemplo, você selecionará uma local superior (pai) se desejar copiar a estrutura inteira de local funcional, que inclui sublocais.
2. Selecione o botão **Copiar a estrutura do local funcional**. O local selecionado na página de lista é mostrado no campo **Copiar de**.
3. Insira o nome do novo local no campo **Novo local funcional**.
4. No campo **Responsável por colar abaixo**, você só deverá inserir uma ID pai se o local que estiver criando fizer parte de uma estrutura de local funcional existente.
5. Clique em **OK**. A nova estrutura de local funcional é mostrada em **Todos os locais funcionais**.

>[!NOTE]
>Ao copiar uma estrutura de local funcional, os estados do ciclo de vida de local funcional na nova estrutura são definidos como o "primeiro estado" que você criou para locais funcionais. Para saber se você pode renomear ou excluir um local funcional usando os botões **Renomear** e **Excluir** em **Todos os locais funcionais**, verifique o estado atual do ciclo de vida do local funcional.

## <a name="delete-a-functional-location"></a>Excluir um local funcional

Um local funcional com sublocais relacionados poderá ser excluído se nenhum ativo tiver sido instalado em locais funcionais que você está tentando excluir e se o estado do ciclo de vida do local funcional atual permitir isso.

1. Em **Todos os locais funcionais**, selecione o local funcional a ser excluído.
2. Se necessário, atualize o local funcional para um estado do ciclo de vida de local funcional que permita a exclusão de um local funcional.
3. Selecione **Excluir**.

>[!NOTE]
>Se você não puder excluir um local funcional, poderá manipular a exclusão configurando um estado do ciclo de vida de local funcional com essa finalidade. Por exemplo, você pode configurar um estágio "Sucateado" ou "Excluído", que não deve ser um estágio ativo, no formulário **Estados do ciclo de vida de local funcional**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]