---
title: Aplicativo do Store Commerce para plataformas móveis
description: Este artigo descreve como começar a usar o aplicativo Microsoft Dynamics 365 Commerce Store Commerce para Android e iOS.
author: stuharg
ms.date: 10/07/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2018-10-29
ms.openlocfilehash: 1f07a130629863ebd9d036378436cf360e90ac26
ms.sourcegitcommit: 98231ff810f41f9fcdc6b536d87e453028aa6db8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2022
ms.locfileid: "9642332"
---
# <a name="store-commerce-app-for-mobile-platforms"></a>Aplicativo do Store Commerce para plataformas móveis

[!include [banner](../includes/banner.md)]

Este artigo descreve como começar a usar os aplicativos Microsoft Dynamics 365 Commerce Store Commerce para Android e iOS.

Os aplicativos móveis do Dynamics 365 Commerce para Android e iOS tornam o processo de implantação de dispositivos móveis de ponto de venda (PDV) completos para seu ambiente de varejo simples e objetivo. Os aplicativos móveis do Store Commerce oferecem todos os recursos e vantagens do aplicativo [Store Commerce para Windows](store-commerce.md) para celulares e tablets. Os aplicativos móveis do Store Commerce podem ser instalados diretamente das lojas de aplicativos Apple e Google Play e não exigem que um desenvolvedor crie um pacote de aplicativos para implantá-los ou atualizá-los. 

Os aplicativos móveis do Store Commerce mantêm a paridade funcional total com os aplicativos híbridos de varejo atuais. Além disso, o Store Commerce para iOS inclui suporte para uma estação de hardware dedicada, para que os dispositivos iOS possam se comunicar com terminais de pagamento em rede, impressoras de recibos e caixas registradoras sem a necessidade de implantar uma estação de hardware compartilhada. 

> [!IMPORTANT]
> Os aplicativos Store Commerce para Windows, Android e iOS são a próxima geração de aplicativos de PDV para o Dynamics 365 Commerce. O atual aplicativo Modern POS (MPOS) e os [aplicativos híbridos de varejo](hybridapp.md) para dispositivos móveis serão preteridos em outubro de 2023. A Microsoft recomenda usar o Store Commerce ou o Cloud POS (CPOS) para todas as novas implantações de PDV. Os clientes existentes devem planejar a migração do aplicativo híbrido de varejo para o Store Commerce. Para obter mais informações sobre a agenda de substituição do MPOS e os aplicativos híbridos de varejo, consulte [Como modernizar a pilha de tecnologia em armazenamento do Dynamics 365 Commerce](https://www.microsoft.com/download/details.aspx?id=103896). 

## <a name="app-architecture"></a>Arquitetura do aplicativo

Os aplicativos móveis do Store Commerce usam a mesma topologia que o aplicativo do Store Commerce para Windows quando implantados no modo híbrido. Os aplicativos móveis do Store Commerce são aplicativos shell que renderizam CPOS diretamente da Commerce Scale Unit (CSU) e se conectam ao Commerce headquarters e Commerce por meio da CSU. O modelo de aplicativo shell permite que os aplicativos Store Commerce ofereçam suporte a uma estação de hardware dedicada para integração direta com um terminal de pagamento, impressora, caixa registradora e outros periféricos. Não é necessário configurar uma estação de hardware compartilhada para usar dispositivos de hardware. 

Para atualizar um aplicativo móvel do Store Commerce, basta atualizar a CSU. Todas as novas funcionalidades e recursos do PDV serão automaticamente selecionados pelo aplicativo. Para obter mais informações sobre como atualizar a CSU, consulte [Aplicar atualizações e extensões à Commerce Scale Unit (nuvem)](../../fin-ops-core/dev-itpro/deployment/update-retail-channel.md).

Os aplicativos shell são atendidos por meio de atualizações da loja de aplicativos. Quando uma versão secundária atingir a disponibilidade geral (GA), a Microsoft a publicará nas lojas de aplicativos. A Microsoft também pode publicar patches entre atualizações de versões secundárias para liberar correções de bugs de alta prioridade.

## <a name="prerequisites"></a>Pré-requisitos

Os aplicativos móveis do Store Commerce exigem o Dynamics 365 Commerce, especificamente os componentes do Commerce headquarters e da CSU. A tabela a seguir lista as versões mínimas de sistema operacional (SO) e CSU exigidas pelos aplicativos móveis Android e iOS. 

| Pré-requisito | Android      | iOS  |
| ------------ | ------------ | ---- |
| Versão do sistema operacional   | 7.0          | 15.0 |
| Versão de CSU  | 9.38.22266.8 | TBD  |

## <a name="install-the-app"></a>Instalar o aplicativo

Você pode instalar os aplicativos móveis do Store Commerce diretamente da Google Play Store ou da Apple App Store. 

- [Aplicativo do Store Commerce para Android](https://aka.ms/storecommerceandroid)
- Aplicativo do Store Commerce para iOS (disponível em breve)

Os pacotes do aplicativo Android (.apk) e do aplicativo Apple (.ipa) também podem ser baixados da biblioteca de ativos compartilhados no Microsoft Dynamics Lifecycle Services. 

## <a name="device-and-register-setup"></a>Configuração da registradora e de dispositivos

Antes que uma registradora possa ser ativada nos aplicativos móveis do Store Commerce, é necessário configurar um dispositivo e uma registradora no Commerce headquarters. Para obter mais informações, consulte [Dispositivos e registradoras](../implementation-considerations-devices.md). 

### <a name="device-setup"></a>Configuração do dispositivo

Siga estas etapas para criar e configurar um novo dispositivo.

1. No Commerce headquarters, acesse **Varejo e Comércio \> Configuração do canal \> Configuração do PDV \> Dispositivos**. 
1. Crie um dispositivo e selecione **Modern POS - Android** ou **Modern POS - iOS** como o tipo de aplicativo, dependendo do aplicativo móvel que estiver implantando. 

    > [!NOTE] 
    > Os tipos de aplicativo **Modern POS - Android** e **Modern POS - iOS** também são usados para implantar os aplicativos híbridos atuais para Android e iOS. Após a descontinuação do MPOS, os rótulos desses tipos de aplicativo serão atualizados para **Store Commerce - Android** e **Modern POS - iOS**. 

### <a name="register-setup"></a>Configuração do registro

É possível criar uma registradora e associá-la ao dispositivo que criou ou associar uma registradora existente ao novo dispositivo. Para obter mais informações sobre registradoras, consulte [Criar e associar registradoras](../tasks/create-associate-registers.md).

### <a name="screen-layout-setup"></a>Configuração do layout da tela

Se você estiver redirecionando um layout de tela incluído nos dados de demonstração fornecidos com sua licença do Dynamics 365 Commerce, o aplicativo Store Commerce selecionará automaticamente o layout compacto incluído se a resolução de tela do dispositivo for inferior a 480 &times; 853 pixels na orientação retrato. No entanto, se estiver criando um layout de tela do zero ou se o dispositivo móvel usar uma resolução maior que a permitida pelo layout compacto, certifique-se de criar uma resolução e grades de botões associadas apropriadas para o celular ou tablet no qual pretende implantar. Para obter mais informações sobre configurações de layout de tela, consulte [Configurações visuais da interface do usuário de PDV](../pos-screen-layouts.md). 

Após a configuração dos dispositivos e registradoras, no Commerce headquarters, acesse **Varejo e comércio \> ID de varejo e comércio \> Agendas de distribuição** e execute o trabalho das registradoras.

## <a name="activate-a-device"></a>Ativar um dispositivo

Siga estas etapas para ativar um dispositivo em um aplicativo móvel do Store Commerce.

1. Abra o aplicativo no dispositivo móvel.
1. Insira a URL do CPOS, que pode ser encontrada na página de detalhes do ambiente em Lifecycle Services ou na página de **Perfis do canal** no Commerce headquarters (**Varejo e comércio \> Configuração do canal \> Perfis do canal**).
1. Entre usando as credenciais de um funcionário com permissão para gerenciar dispositivos.
1. Selecione a loja que está associada ao cadastro criado ou reutilizado no Commerce headquarters.
1. Selecione a registradora que você associou ao dispositivo criado no Commerce headquarters.
1. O seu dispositivo deve estar ativado agora. Acesse a caixa registradora usando a ID do operador e a senha do funcionário associado à loja selecionada. 

Para obter mais informações sobre a ativação do dispositivo, consulte [Ativação do dispositivo de ponto de venda (PDV)](retail-device-activation.md#activate-a-modern-pos-or-cloud-pos-device-by-using-guided-activation).

## <a name="feature-parity-with-store-commerce-for-windows"></a>Paridade de recursos com Store Commerce para Windows

A tabela a seguir compara os recursos do aplicativo Store Commerce nas plataformas Windows, Android e iOS.

| Recurso                                                                               | Windows | Android | iOS |
| ------------------------------------------------------------------------------------- | ------- | ------- | --- |
| Estação de hardware dedicada                                                            | Sim     | Sim     | Sim |
| Estação de hardware compartilhada                                                               | Sim     | Sim     | Sim |
| Comunicação com periféricos em rede (terminal de pagamento, impressora e caixa registradora) | Sim     | Sim     | Sim |
| Periféricos OLE para ponto de venda (OPOS) por meio de uma estação de hardware local             | Sim     | Número      | Número  |
| Modo offline                                                                          | Sim     | Número      | Número  |

## <a name="additional-resources"></a>Recursos adicionais

[Aplicativo Store Commerce](store-commerce.md)

[Escolher entre o Store Commerce e o Cloud POS](../mpos-or-cpos.md)

[Solucionar problemas de configuração e instalação do Store Commerce](../troubleshoot/store-commerce-setup-installation.md)
