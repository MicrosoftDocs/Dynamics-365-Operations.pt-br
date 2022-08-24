---
title: Copiar um site de comércio eletrônico
description: Este artigo descreve como copiar um site de comércio eletrônico existente em ambientes de comércio eletrônico ou entre eles no criador de sites do Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 06/03/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 9b74e0d48be29272b893c855c229e4003f0c161e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276276"
---
# <a name="copy-an-e-commerce-site"></a>Copiar um site de comércio eletrônico

[!include [banner](../includes/banner.md)]

Este artigo descreve como copiar um site de comércio eletrônico existente em ambientes de comércio eletrônico ou entre eles no criador de sites do Microsoft Dynamics 365 Commerce.

O Dynamics 365 Commerce oferece suporte a locais de cópia ou clonagem como uma operação de auto-atendimento no criador de sites do Commerce. Os sites podem ser copiados em um único ambiente de comércio eletrônico ou entre dois desses ambientes. O usuário que inicia a operação de cópia de site deve ser um administrador de locatários nos ambientes de comércio eletrônico de origem e de destino.

A operação de cópia de site copia todo o conteúdo de comércio eletrônico do site de origem. Esse conteúdo inclui páginas, fragmentos, modelos, URLs e ativos. Antes que um novo site possa ser usado, ele deve ser inicializado por meio do processo FRE (primeira execução da experiência). Os canais podem ser mapeados e gerenciados no criador de sites, em **Configurações do Site \> Canais**.

A duração da operação de cópia do site depende basicamente do número de ativos no site de origem. No caso de sites excepcionalmente grandes, recomendamos que você considere o uso da operação de cópia do ambiente. (Essa operação também é conhecida como a operação de portabilidade de dados).

> [!NOTE]
> - O site de origem será somente leitura durante a operação de cópia do site.
> - Somente as versões publicadas de documentos são copiadas. Se nenhuma versão tiver sido publicada, somente as versões mais recentes serão copiadas.
> - O histórico de versões para o conteúdo não estará disponível no site de destino.

## <a name="copy-a-site-within-an-e-commerce-environment"></a>Copiar um site em um ambiente de comércio eletrônico

Para copiar um site em um ambiente de comércio eletrônico, siga estas etapas.

1. Entre no criador de sites do ambiente em que você deseja executar a operação de cópia.
1. Abra a visualização de lista de sites selecionando **Seletor de site** no canto superior direito e, depois, selecionando **Gerenciar sites**.
1. Encontre o site que você deseja copiar ou clonar e selecione-o marcando a caixa de seleção ao lado do nome do site.
1. Na barra de comandos, selecione **Copiar site**.
1. No menu do submenu **Copiar site**, no campo **Nome do novo site**, insira um nome para o novo site. O nome do novo site deve ser exclusivo no ambiente de comércio eletrônico. Os campos **Locatário de Origem** e **Site de Origem** são definidos automaticamente com as informações do locatário atual e do site selecionado.
1. Selecione **Criar cópia**.

Depois que as informações forem validadas, uma notificação indicará que um novo trabalho de cópia do site foi criado. Você pode monitorar o andamento do trabalho no [painel direito da página **Trabalhos de locatário**](#monitor-the-site-copy-operation). Quando a operação de cópia for concluída com êxito, o novo site será exibido na lista de sites na exibição de lista de sites.

A ilustração a seguir mostra um exemplo do menu do submenu **Copiar site** no criador de sites.

![Menu do submenu Copiar site no criador de sites.](media/site-copy_1.png)

## <a name="copy-a-site-between-two-e-commerce-environments"></a>Copiar um site entre dois ambientes de comércio eletrônico

Para copiar um site entre dois ambientes de comércio eletrônico, siga estas etapas.

1. Entre no criador de sites do ambiente de comércio eletrônico de destino.
1. Na barra de comandos, selecione **Copiar site**.
1. No menu do submenu **Copiar site**, no campo **Nome do novo site**, insira um nome para o novo site. O nome do novo site deve ser exclusivo no ambiente de comércio eletrônico.
1. No campo **Locatário de origem**, selecione o nome do locatário de origem.
1. No campo **Site de origem**, selecione o site de origem.
1. Selecione **Criar cópia**.

> [!NOTE]
> As permissões de administrador de locatário são necessárias para os ambientes de comércio eletrônico de origem e de destino.

Depois que as informações forem validadas, uma notificação indicará que um novo trabalho de cópia do site foi criado. Você pode monitorar o andamento do trabalho no [painel direito da página **Trabalhos de locatário**](#monitor-the-site-copy-operation). Quando a operação de cópia for concluída com êxito, o novo site será exibido na lista de sites na exibição de lista de sites.

## <a name="map-channels-during-the-site-copy-operation-optional"></a>Mapear canais durante a operação de cópia de site (opcional)

Os canais de origem e as localidades podem ser mapeadas para canais e locais de destino como parte da operação de cópia do site. Se o mapeamento de canal for feito como parte da operação de cópia de site, a inicialização do site usando o processo FRE e a configuração dos canais nas configurações do site não serão necessárias. 

Para mapear todos os canais e localidades "como estão" (1 para 1) no criador de sites, siga estas etapas.

1. Abra a visualização de lista de sites selecionando **Seletor de site** no canto superior direito e, depois, selecionando **Gerenciar sites**.
1. Encontre o site que você deseja copiar ou clonar e selecione-o marcando a caixa de seleção ao lado do nome do site.
1. Na barra de comandos, selecione **Copiar site**.
1. No menu do submenu **Copiar site**, informe valores para **Novo nome do site**, **Locatário da origem** e **Site de origem** (se ainda não estiver presente).
1. Selecione **Adicionar mapeamentos de canal**.
1. No menu do submenu **Configurar canais e localidades do site**, selecione **Canal de origem** e selecione o canal de origem.  
1. Selecione **Canal de destino** e, em seguida, selecione o mesmo canal que o canal de origem. 
1. Selecione **Adicionar localidade**.
1. Selecione **Localidade de origem** e selecione a localidade de origem.
1. Selecione **Localidade de destino** e, em seguida, selecione a mesma localidade da localidade de origem. 
1. Para **Caminho da URL**, insira um caminho de URL exclusivo que não esteja sendo usado no momento no ambiente de destino.
1. Repita as etapas de 8 a 11 para cada localidade a ser mapeada para o canal.
1. Selecione **Aplicar**.
1. Repita as etapas de 6 a 11 para cada canal de origem.
1. Selecione **Fechar**.
1. Revise a configuração para obter precisão e selecione **Copiar site**.

> [!NOTE]
> Todos os canais e localidades de origem devem ser mapeados e só podem ser mapeados uma vez.

## <a name="monitor-the-site-copy-operation"></a>Monitorar a operação de cópia do site

Para monitorar o progresso da operação de cópia do site, siga estas etapas.

1. Entre no criador de sites do ambiente de comércio eletrônico de destino.
1. No painel à esquerda, selecione **Trabalhos de locatário**.
1. Na página **Trabalhos de locatário**, localize e selecione o trabalho de cópia do site na lista. Um painel é exibido à direita e mostra o status e os detalhes do trabalho selecionado.

Você pode cancelar um trabalho que tenha um status **Em andamento**. Selecione o trabalho na lista e, em seguida, selecione **Cancelar** na barra de comandos.

Você pode repetir um trabalho que tenha um status de **Com falha** ou **Concluído com erros**. Selecione o trabalho na lista e, em seguida, selecione **Tentar novamente** na barra de comandos.

> [!NOTE]
> O processamento de ativos de vídeo pode continuar depois que um trabalho de cópia do site é concluído.

A ilustração a seguir mostra um exemplo do painel direito da página **Trabalhos de locatário** no criador de sites.

![Detalhes do trabalho no painel direito da página Trabalhos do Locatário no criador de sites.](media/site-copy_2.png)

## <a name="initialize-a-new-site-by-using-the-fre-process"></a>Inicializar um novo site usando o processo FRE

Antes que o novo site possa ser usado, ele deve ser inicializado por meio do processo FRE.

Para inicializar um novo site usando o processo FRE, siga estas etapas.

1. Entre no criador de sites do novo site.
1. Abra a visualização de lista de sites selecionando **Seletor de site** no canto superior direito e, depois, selecionando **Gerenciar sites**.
1. Localize e selecione o novo site que você deseja inicializar.
1. Na caixa de diálogo **Configurar o site**, no campo **Selecionar um domínio**, selecione um domínio. Todos os domínios associados ao ambiente de comércio eletrônico durante a inicialização estão disponíveis para seleção.
1. No campo **Selecionar um canal padrão**, selecione o canal da loja online associado. O canal selecionado fornecerá classificações e outras informações armazenadas no Commerce headquarters.
1. No campo **Selecionar um idioma padrão**, selecione o idioma de criação padrão. Todos os idiomas que foram configurados para o canal de loja online selecionado estão disponíveis para seleção.
1. No campo **Caminho**, o valor consiste no domínio base e um caminho de URL opcional que você pode inserir. Você pode deixar o caminho da URL em branco se o canal for fornecido por meio da raiz do domínio ou se desejar inserir essas informações posteriormente na exibição de configuração do canal no criador de sites. O caminho do site deve ser exclusivo no ambiente de comércio eletrônico.
1. Selecione **OK**. O site é inicializado com as informações fornecidas, e você é encaminhado para a exibição de gerenciamento do site.

A ilustração a seguir mostra um exemplo da caixa de diálogo **Configurar o site** no criador de sites.

![Configure a caixa de diálogo do site no criador de sites.](media/site-copy_3.png)

## <a name="additional-resources"></a>Recursos adicionais

[Configurar seu nome de domínio](configure-your-domain-name.md)

[Implantar um novo locatário de comércio eletrônico](deploy-ecommerce-site.md)

[Associar um site do Dynamics 365 Commerce a um canal online](associate-site-online-store.md)

[Gerenciar arquivos robots.txt](manage-robots-txt-files.md)

[Carregar redirecionamentos de URL em massa](upload-bulk-redirects.md)

[Configurar um locatário B2C do Commerce](set-up-b2c-tenant.md)

[Configurar páginas personalizadas para logons dos usuários](custom-pages-user-logins.md)

[Configurar múltiplos locatários B2C em um ambiente do Commerce](configure-multi-b2c-tenants.md)

[Adicionar suporte para uma rede de entrega de conteúdo (CDN)](add-cdn-support.md)

[Habilitar detecção de lojas com base na localização](enable-store-detection.md)
