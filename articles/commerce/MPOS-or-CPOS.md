---
title: Escolher entre o Store Commerce e o Cloud POS
description: Este artigo explica as principais diferenças entre o Store Commerce e o Cloud POS e descreve vários fatores que os varejistas que implementam o Dynamics 365 Commerce devem considerar para fazer a melhor escolha de acordo com suas necessidades.
author: josaw1
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2017-10-12
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: bbb5f3d4c61907243bed404f3ab7bea05c78b1c0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276445"
---
# <a name="choose-between-store-commerce-and-cloud-pos"></a>Escolher entre o Store Commerce e o Cloud POS

[!include [banner](includes/banner.md)]

Este artigo explica as principais diferenças entre o Store Commerce e o Cloud POS e descreve vários fatores que os varejistas que implementam o Dynamics 365 Commerce devem considerar para fazer a melhor escolha de acordo com suas necessidades. Este tópico oferece orientação, dicas e experiência adicional de implementadores sobre fatores que devem ser considerados ao implantar o Dynamics 365 Commerce. Ao examinar e seguir essas orientações como parte do processo de implantação, os implementadores poderão evitar problemas que possam afetar o desempenho e a satisfação do usuário.

## <a name="insights"></a>Insights

O Commerce fornece uma ampla variedade de opções de implantação e de topologia. Portanto, os varejistas podem escolher os componentes e a configuração que melhor atendem a suas necessidades tecnológicas e empresariais. Um aspecto de implementação que requer considerações é a escolha da plataforma e do fator forma para o componente de ponto de venda (PDV).

### <a name="pos-platform-and-form-factor-considerations"></a>Considerações de fator forma e plataforma de PDV

O Commerce oferece suporte às seguintes opções de PDV:

- Store Commerce para Microsoft Windows
- Store Commerce para iOS e Android
- Cloud POS (CPOS) que oferece suporte aos navegadores do Microsoft Edge e Google Chrome
- Modern POS (MPOS) para Microsoft Windows (MPOS será substituído em outubro de 2023). 

Em todos os casos, o POS (Store Commerce e CPOS) compartilha o mesmo código básico de aplicativo. Este ponto é importante pelos seguintes motivos:

- A interface do usuário (IU) é consistente, independentemente da plataforma ou do fator forma.
- A maioria das capacidades funcionais é a mesma, independentemente da plataforma ou do fator forma. No entanto, há alguns diferenças importantes. Essas diferenças serão observadas neste artigo.
- Em cada loja, as variações de PDV podem ser combinadas e executadas simultaneamente. Por exemplo, para seus registros principais, um varejista pode usar o Store Commerce em computadores que executam o Windows. No entanto, o varejista pode complementar esses registros com terminais baseados em navegador ou dispositivos móveis.
- As personalizações e extensões podem ser usadas facilmente entre as plataformas e os fatores forma. Como o código básico do aplicativo é compartilhado, a maioria da personalizações pode ser implementada apenas um vez.

### <a name="store-commerce-vs-cpos"></a>Store Commerce x CPOS

Embora o Store Commerce e o CPOS sejam em grande parte os mesmos, existem algumas diferenças importantes que você deve compreender.

#### <a name="store-commerce"></a>Store Commerce

O Store Commerce é um aplicativo de desktop que é instalado e atendido em um dispositivo.

- **Windows** – o aplicativo do Store Commerce para Windows contém todos os códigos do aplicativo, Commerce Runtime (CRT) e o Hardware Station (HWS).
- **iOS/Android** – Nessas plataformas, o aplicativo funciona como um host para o código do aplicativo de CPOS. Em outras palavras, o código do aplicativo será obtido do servidor CPOS hospedado no Commerce Scale Unit. Para obter mais informações, consulte [Visão geral da Commerce Scale Unit](dev-itpro/retail-store-system-begin.md).

#### <a name="cpos"></a>CPOS

Como o CPOS é executado em um navegador, o aplicativo não é instalado no dispositivo. Em vez disso, o navegador acessa o código do aplicativo do servidor do CPOS. Portanto, o CPOS não pode acessar diretamente o hardware do PDV ou funcionar em um estado offline.

### <a name="store-deployment-considerations"></a>Considerações de implantação de loja

Além de uma plataforma e um fator forma, os varejistas também devem escolher uma opção de implantação na loja. A tabela a seguir mostra as configurações disponíveis para cada opção de PDV.

| Aplicativo do PDV            | Commerce Scale Unit | Offline disponível | Suporte local a HWS |
|----------------------------|---------------------|-------------------|-------------------|
| Store Commerce para Windows | Nuvem ou RSSU       | Sim               | Sim               |
| Store Commerce para Android | Nuvem ou RSSU       | Número                | Sim               |
| Store Commerce para iOS     | Nuvem ou RSSU       | Número                | Número                |
| PDV em Nuvem                  | Nuvem ou RSSU       | Número                | Número                |

#### <a name="commerce-scale-unit"></a>Commerce Scale Unit

O Commerce Scale Unit é um componente que hospeda o CRT. O CRT contém toda a lógica comercial que o PDV usa e fornece acesso ao banco de dados do canal. Enquanto estão online, todos os clientes de PDV na loja usam o Commerce Scale Unit. O Commerce Scale Unit pode ser implantado na nuvem ou na loja.

#### <a name="offline-mode"></a>Modo offline

O Store Commerce para Windows oferece suporte ao modo off-line. No modo offline, o PDV pode continuar a processar vendas mesmo desconectado do servidor do Commerce Scale Unit.. Ele pode ser sincronizado com o banco de dados do canal quando a conectividade é restaurada. O Store Commerce usa sua própria instância inserida do CRT e utiliza temporariamente sua própria fonte de dados local (banco de dados do SQL Server offline). Para obter mais informações sobre recursos offline, consulte [Recursos offline do PDV](pos-offline-functionality.md).

### <a name="pos-peripheralhardware-considerations"></a>Considerações sobre periférico/hardware de PDV

Os varejistas também devem considerar como o PDV acessará os dispositivos e os periféricos como impressoras, caixas registradoras e terminais de pagamento. As estações de hardware podem ser dedicadas a um registro de PDV ou compartilhadas entre os registros de uma loja.

| Aplicativo do PDV            | OPOS do HWS local | Periféricos de rede | Suporte a HWS compartilhado |
|----------------------------|----------------|---------------------|--------------------|
| Store Commerce para Windows | Sim            | Sim                 | Sim                |
| Store Commerce para Android | Número             | Sim                 | Sim                |
| Store Commerce para iOS     | Número             | Número                  | Sim                |
| PDV em Nuvem                  | Número             | Número                  | Sim                |

Para obter mais informações sobre como instalar estações de hardware, consulte [Configurar e instalar uma estação de hardware do Retail](retail-hardware-station-configuration-installation.md).

## <a name="implementation-considerations"></a>Considerações de implementação

Considere as seguintes informações enquanto planeja sua implementação de PDV nas suas lojas:

- **Requisitos funcionais** – Os principais processos de negócios e as capacidades são os mesmos, independentemente da plataforma, fator forma e topologia de implantação. Portanto, a maioria dos varejistas não precisa considerar requisitos funcionais quando planeja a implementação.
- **Conectividade** – A disponibilidade de rede (ampla área de rede \[WAN\] e rede local \[LAN\]) é um fator importante que requer considerações. Os benefícios que uma solução hospedada em nuvem de superfície zero traz em termos de custo e simplicidade serão perdidos se o sistema não estiver disponível para processos essenciais aos negócios.

    A menos que a conectividade de um dispositivo fornecido seja muito segura e resiliente, ou a menos que um determinado tempo de inatividade seja aceitável para o varejista, recomendamos uma das seguintes opções:

    - Use o Store Commerce no Windows e ative o modo offline.
    - Implante um Commerce Scale Unit local.

    Essas duas opções não são mutuamente exclusivas. Para a topologia mais confiável, os varejistas podem implantar uma RSSU local para reduzir a dependência da conectividade com a Internet ou a disponibilidade do Azure. Também é possível implantar registros de PDV onde o modo offline estiver ativado se houver um problema com o servidor ou rede local.

- **Dispositivos de hardware/periféricos** – Um aspecto importante de um sistema Retail POS é sua capacidade de usar periféricos de PDV, como impressoras, caixas registradoras e terminais de pagamento. Embora todas as opções disponíveis de PDV possam usar dispositivos periféricos, somente o Store Commerce para Windows pode suportá-las diretamente. Para todos os outros aplicativos, uma ou mais estações de hardware são necessárias. Embora essa abordagem adicione flexibilidade, componentes adicionais devem ser implantados, configurados e ter manutenção.
- **Requisitos do sistema** – Os requisitos do sistema para o aplicativo de PDV variam. Lembre-se de verificar as informações mais recentes antes de fazer sua escolha. Por exemplo, como o CPOS é executado em um navegador, ele oferece suporte a uma ampla variedade de sistemas operacionais. Para obter mais informações sobre os requisitos do sistema, consulte [Requisitos de sistema para implantações na nuvem](../fin-ops-core/fin-ops/get-started/system-requirements.md).
- **Implantação e manutenção** – A complexidade dos requisitos de implantação e manutenção pode variar, dependendo das escolhas de aplicativos e implantação. Por exemplo, para uma implementação de CPOS hospedada em nuvem, não é necessário instalação e atualização em cada dispositivo. Portanto, essa abordagem reduz muito a complexidade e os custos. No entanto, se você implantar o Store Commerce em cada registro e habilitar o modo offline, e também implantar estações de hardware compartilhadas, aumentará muito o número de pontos de extremidade que devem ser gerenciados.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
