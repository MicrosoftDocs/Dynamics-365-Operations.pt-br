---
title: Configurações do usuário do dispositivo móvel
description: Este artigo explica como gerenciar configurações de usuário do dispositivo móvel para trabalhadores de depósito.
author: Mirzaab
ms.date: 02/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppDeviceBrand,WHSMobileAppUserDisplaySettings
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 15f9ce1768e1ed9dc6f7e84d245082b46a7f122c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882334"
---
# <a name="mobile-device-user-settings"></a>Configurações do usuário do dispositivo móvel

[!include [banner](../../includes/banner.md)]

O novo aplicativo móvel Warehouse Management tem um conjunto de configurações específicas do aplicativo que ajudam a personalizar a experiência do usuário. Como o aplicativo pode ser usado em dispositivos com tamanhos de tela e configurações diferentes (como tablet, smartphone ou portátil), pode ser útil gerenciar centralmente essas configurações no Microsoft Dynamics 365 Supply Chain Management.

O recurso de *configurações de usuário do dispositivo móvel* permite definir as configurações de usuário globais que serão usadas em todos os dispositivos. Você também pode definir configurações de usuário mais granulares para marcas de dispositivos individuais, modelos de dispositivo e/ou trabalhadores. Quando um trabalhador entra no aplicativo móvel Warehouse Management, o aplicativo busca e aplica o perfil de configurações mais específico armazenado no Supply Chain Management para a marca, o dispositivo e/ou ID de usuário correspondente.

Este recurso pode ajudar os trabalhadores a iniciar de forma mais rápida sempre que começarem a usar um novo dispositivo. Eis alguns exemplos:

- Os administradores podem estabelecer um conjunto de preferências que funcione melhor para dispositivos de um fabricante específico e/ou para modelos de dispositivos específicos. Portanto, os trabalhadores podem começar com um novo dispositivo sem necessariamente precisar alterar as configurações.
- Se a sua empresa tiver um pool de dispositivos idênticos que são compartilhados entre trabalhadores, eles verão a configuração preferencial sempre que entrarem, mesmo se nunca tiverem usado o dispositivo físico específico selecionado em um determinado dia.
- No Supply Chain Management, os administradores podem exibir e editar todas as configurações armazenadas, mesmo para trabalhadores individuais. Esse recurso pode ajudá-los a solucionar problemas ou ajustar novos recursos.

> [!IMPORTANT]
> O recurso *configurações de usuário do dispositivo móvel* é aplicável somente ao novo aplicativo móvel Warehouse Management. Ele não funciona com o antigo aplicativo de depósito.

## <a name="turn-the-mobile-device-user-settings-feature-on-or-off"></a>Ativar ou desativar o recurso de configurações de usuário do dispositivo móvel

Para usar a funcionalidade descrita neste artigo, o recurso *Configurações de usuário, ícones e títulos de etapas para o novo aplicativo de depósito* deve estar ativado para o seu sistema. A partir do Supply Chain Management 10.0.25, este recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.25, os administradores poderão ativar ou desativar essa funcionalidade procurando o recurso *Configurações de usuário, ícones e títulos de etapas do novo aplicativo de depósito* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="create-and-manage-user-settings"></a>Criar e gerenciar configurações de usuário

Use a página **Configurações de usuário do dispositivo móvel** para criar, exibir e gerenciar perfis de configuração em todos os níveis de granularidade. Na primeira vez que um trabalhador edita as configurações de usuário em um novo dispositivo, um novo perfil é adicionado automaticamente nesta página, caso ainda não exista. Esse perfil será atualizado sempre que o trabalhador fizer uma alteração.

Você também pode definir um perfil de configurações que se aplica a todas as marcas de dispositivos, modelos de dispositivos e/ou trabalhadores. Em seguida, é possível aumentar a granularidade aplicando configurações mais específicas para marcas individuais, modelos e/ou trabalhadores.

Siga estas etapas para criar e gerenciar configurações de usuário para dispositivos móveis.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Configurações de usuário do dispositivo móvel**.
1. Selecione um perfil de configurações de usuário existente no painel de lista para abrir o registro. Como alternativa, selecione **Novo** no Painel de Ações para criar um perfil.

    Cada perfil no painel de lista é identificado para indicar a marca, o modelo e/ou a ID de usuário à qual o perfil se aplica. Perfis mais gerais têm um valor *Todos* para algumas ou todas essas características.

1. Na seção do cabeçalho do registro do perfil de configurações novo ou selecionado, defina os seguintes campos:

    - **Nome da marca do dispositivo** – Selecione o nome da marca do dispositivo ao qual o perfil deve ser aplicado. Se o perfil deve ser aplicado a todas as marcas, deixe este campo em branco. A lista de valores inclui todas as marcas que foram definidas no sistema. Para obter informações sobre como definir a lista de marcas, consulte a próxima seção.
    - **ID do modelo do dispositivo** – Selecione o modelo do dispositivo ao qual o perfil deve ser aplicado. Se o perfil deve ser aplicado a todos os modelos da marca selecionada, deixe este campo em branco. A lista de valores inclui todos os modelos que foram definidos para a marca selecionada no campo **Nome da marca do dispositivo**. Para obter informações sobre como definir a lista de modelos de cada marca, consulte a próxima seção.
    - **ID de usuário** – Selecione a ID de usuário do trabalhador de depósito ao qual o perfil de configuração deve ser aplicado. Se o perfil deve ser aplicado a todos os trabalhadores, deixe este campo em branco.

1. Na Guia Rápida **Geral**, defina os seguintes campos:

    - **Posição do botão** – Selecione como os botões devem ser posicionados no dispositivo. Os elementos no aplicativo serão movidos para melhor se ajustarem à preferência ou configuração de destro/canhoto do trabalhador. As opções disponíveis são *Inferior à direita (padrão)*, *Inferior à esquerda*, *Superior à direita* e *Superior à esquerda*.
    - **Orientação da tela** – Selecione a orientação da tela que deve ser aplicada por padrão no aplicativo.
    - **Digitalizar com câmera** – Defina esta opção como *Sim* para usar a câmera do dispositivo para digitalizar campos de entrada em que o modo de entrada preferencial está definido como *Digitalização*. Se o dispositivo tiver um scanner interno, defina esta opção como *Não* para usar o scanner.
    - **Mostrar foto do produto** – Selecione se as fotos do produto devem ser mostradas caso estejam disponíveis para o produto liberado. Para obter mais informações sobre como adicionar imagens de produto, consulte [Adicionar uma imagem a um produto](../pim/tasks/add-image-product.md).
    - **Tema de cores de exibição** – Selecione um tema de cores para o dispositivo.
    - **Nível de som** – Selecione o nível de som para o dispositivo. Selecione um valor entre zero (0) e 10. Um valor igual a *0* representa nenhum som, e um valor igual a *10* representa o volume máximo. O valor padrão é *4*.
    - **Nível de vibração** – Selecione o nível de vibração para o dispositivo. Selecione um valor entre zero (0) e 5. Um valor igual a *0* representa nenhuma vibração, e um valor igual a *5* representa o nível de vibração máximo. O valor padrão é *1*.
    - **Porcentagem da escala de texto** – Especifique o tamanho do texto como porcentagem do tamanho padrão. Insira um valor entre 70 e 400. Um valor igual a *70* representa a menor escala de texto, e um valor igual a *400* representa a maior escala de texto. O valor padrão é *100*.
    - **Porcentagem da escala do botão** – Especifique o tamanho do botão como porcentagem do tamanho padrão. Insira um valor entre 50 e 200. Um valor igual a *50* representa a menor escala do botão, e um valor igual a *200* representa a maior escala do botão. O valor padrão é *100*.

## <a name="create-and-manage-mobile-device-brands"></a>Criar e gerenciar marcas de dispositivo móvel

Use a página **Marcas de dispositivo móvel** para exibir, criar e gerenciar as marcas e os modelos do dispositivo que podem ser usados nos perfis de configuração. O aplicativo móvel automaticamente busca e envia o nome da marca local e a ID do modelo na primeira vez em que um trabalhador edita as configurações em um determinado dispositivo. Portanto, a maioria desses registros geralmente será gerada automaticamente. No entanto, você também pode gerenciar todos os registros desta página. Por exemplo, você pode fornecer descrições mais úteis para cada marca e modelo para ajudar a diferenciar IDs de modelos semelhantes ou crípticos.

Siga estas etapas para criar e gerenciar marcas e modelos de dispositivos móveis.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Marcas de dispositivo móvel**.
1. No painel de lista, selecione uma marca de dispositivo móvel para abrir seu registro. Como alternativa, selecione **Novo** no Painel de Ações para criar uma marca.
1. Na seção do cabeçalho do registro da marca do dispositivo novo ou selecionado, defina os seguintes campos:

    - **Nome da marca do dispositivo** – O nome da marca do dispositivo, como *Microsoft Corporation*.
    - **Descrição** – Você pode inserir uma descrição para ajudar a diferenciar nomes de marcas.

1. A Guia Rápida **Modelos de dispositivo móvel** mostra todos os modelos da marca de dispositivo selecionada. Use os botões da barra de ferramentas para adicionar linhas à grade ou para removê-las. Para cada linha, você pode definir os seguintes campos:

    - **ID do modelo do dispositivo** – A ID do modelo do dispositivo, como *Surface Book 2*.
    - **Descrição** – Você pode inserir uma descrição para ajudar a diferenciar IDs de modelos.

## <a name="additional-resources"></a>Recursos adicionais

- [Instalar e conectar o aplicativo móvel Warehouse Management](install-configure-warehouse-management-app.md)
- [Atribuir títulos e ícones de etapa ao aplicativo móvel Warehouse Management](step-icons-titles.md)