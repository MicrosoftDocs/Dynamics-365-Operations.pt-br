---
title: Escolha entre Modern POS (MPOS) e PDV em Nuvem
description: Este tópico explica as principais diferenças entre o Modern POS e o PDV em Nuvem. Ele também descreve vários fatores que os varejistas que estão implementando o Dynamics 365 Commerce devem considerar para ajudá-los a fazer a melhor escolha de acordo com seus requisitos.
author: jblucher
manager: AnnBe
ms.date: 10/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-10-12
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 508fda28d8f815f030e7b163709393f70904a5fd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410097"
---
# <a name="choose-between-modern-pos-mpos-and-cloud-pos"></a>Escolha entre Modern POS (MPOS) e PDV em Nuvem

[!include [banner](includes/banner.md)]

Este tópico oferece orientação, dicas e experiência adicional de implementadores sobre fatores que devem ser considerados ao implantar o Dynamics 365 Commerce. Ao examinar e seguir essas orientações como parte do processo de implantação, os implementadores poderão evitar problemas que possam afetar o desempenho e a satisfação do usuário.

## <a name="insights"></a>Insights

O Commerce fornece uma ampla variedade de opções de implantação e de topologia. Portanto, os varejistas podem escolher os componentes e a configuração que melhor atendem a suas necessidades tecnológicas e empresariais. Um aspecto de implementação que requer considerações é a escolha da plataforma e do fator forma para o componente de ponto de venda (PDV).

### <a name="pos-platform-and-form-factor-considerations"></a>Considerações de fator forma e plataforma de PDV

O Commerce oferece suporte às seguintes opções de PDV:

- POS moderno (MPOS) para Microsoft Windows
- MPOS para Telefone do Microsoft Windows
- MPOS para tablet Apple iPad ou Google Android
- PDV em Nuvem (CPOS) que oferece suporte aos navegadores do Microsoft Edge, Internet Explorer e Google Chrome

Em todos os casos, o PDV (MPOS e CPOS) compartilha o mesmo código básico de aplicativo. Este ponto é importante pelos seguintes motivos:

- A interface do usuário (IU) é consistente, independentemente da plataforma ou do fator forma.
- A maioria das capacidades funcionais é a mesma, independentemente da plataforma ou do fator forma. No entanto, há alguns diferenças importantes. Essas diferenças serão observadas neste tópico.
- Em uma determinada loja, as variações de PDV podem ser combinadas e executadas simultaneamente. Por exemplo, para seus registros principais, um varejista pode usar MPOS em computadores que executam o Windows. No entanto, o varejista pode complementar esses registros com terminais baseados em navegador ou dispositivos móveis.
- As personalizações e extensões podem ser usadas facilmente entre as plataformas e os fatores forma. Como o código básico do aplicativo é compartilhado, a maioria da personalizações pode ser implementada apenas um vez.

### <a name="mpos-vs-cpos"></a>MPOS vs. CPOS

Embora o MPOS e o CPOS sejam em grande parte os mesmos, existem algumas diferenças importantes que você deve compreender.

#### <a name="mpos"></a>MPOS

O MPOS em um dispositivo Windows, iOS ou Android é um aplicativo que é empacotado, instalado e atendido no dispositivo.

- **Windows** – O MPOS para aplicativo do Windows contém todos os códigos do aplicativo e o tempo de execução de comércio inserido (CRT). 
- **iOS/Android** – Nessas plataformas, o aplicativo funciona como um host para o código do aplicativo de CPOS. Em outras palavras, o código do aplicativo será obtido do servidor CPOS no Microsoft Azure ou no Commerce Scale Unit.. Para obter mais informações, consulte [Visão geral da Commerce Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/retail-store-system-begin).

#### <a name="cpos"></a>CPOS

Como o CPOS é executado em um navegador, o aplicativo não é instalado no dispositivo. Em vez disso, o navegador acessa o código do aplicativo do servidor do CPOS. Portanto, o CPOS não pode acessar diretamente o hardware do PDV ou funcionar em um estado offline.

### <a name="store-deployment-considerations"></a>Considerações de implantação de loja

Além de uma plataforma e um fator forma, os varejistas também devem escolher uma opção de implantação na loja. A tabela a seguir mostra as configurações disponíveis para cada opção de PDV.

| Aplicativo do PDV         | Commerce Scale Unit | Offline disponível |
|-------------------------|---------------|-------------------|
| MPOS para Windows        | Nuvem ou RSSU | Sim               |
| MPOS para iOS ou Android | Nuvem ou RSSU | Não                |
| PDV em Nuvem               | Nuvem ou RSSU | Não                |

#### <a name="commerce-scale-unit"></a>Commerce Scale Unit

O Commerce Scale Unit é um componente que hospeda o CRT. O CRT contém toda a lógica comercial que o PDV usa e fornece acesso ao banco de dados do canal. Enquanto estão online, todos os clientes de PDV na loja usam o Commerce Scale Unit. O Commerce Scale Unit pode ser implantado na nuvem ou na loja.

#### <a name="offline-mode"></a>Modo offline

MPOS para Windows oferece suporte ao modo offline. No modo offline, o PDV pode continuar a processar vendas mesmo desconectado do servidor do Commerce Scale Unit.. Ele pode ser sincronizado com o banco de dados do canal quando a conectividade é restaurada. O MPOS usa sua própria instância inserida do CRT e utiliza temporariamente sua própria fonte de dados local (banco de dados do SQL Server offline). Para obter mais informações sobre recursos offline, consulte [Recursos offline do PDV](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-offline-functionality).

### <a name="pos-peripheralhardware-considerations"></a>Considerações sobre periférico/hardware de PDV

Os varejistas também devem considerar como o PDV acessará os dispositivos e os periféricos como impressoras, caixas registradoras e terminais de pagamento. Somente o MPOS para Windows permite a comunicação direta com esses dispositivos. MPOS para Windows Phone, iOS ou Android e PDV em Nuvem exigem uma estação de hardware para acessar esses dispositivos. As estações de hardware podem ser dedicadas a um registro de PDV ou compartilhadas entre os registros de uma loja. Para obter mais informações sobre como instalar estações de hardware, consulte [Configurar e instalar uma estação de hardware do Retail](https://docs.microsoft.com/dynamics365/unified-operations/retail/retail-hardware-station-configuration-installation).

## <a name="implementation-considerations"></a>Considerações de implementação

Considere as seguintes informações enquanto planeja sua implementação de PDV nas suas lojas:

- **Requisitos funcionais** – Os principais processos de negócios e as capacidades são os mesmos, independentemente da plataforma, fator forma e topologia de implantação. Portanto, a maioria dos varejistas não precisa considerar requisitos funcionais quando planeja a implementação.
- **Conectividade** – A disponibilidade de rede (ampla área de rede \[WAN\] e rede local \[LAN\]) é um fator importante que requer considerações. Os benefícios que uma solução hospedada em nuvem de superfície zero traz em termos de custo e simplicidade serão perdidos se o sistema não estiver disponível para processos essenciais aos negócios.

    A menos que a conectividade de um dispositivo fornecido seja muito segura e resiliente, ou a menos que um determinado tempo de inatividade seja aceitável para o varejista, recomendamos uma das seguintes opções:

    - Use MPOS no Windows e ative o modo offline.
    - Implante um Commerce Scale Unit local.

    Essas duas opções não são mutuamente exclusivas. Para a topologia mais confiável, os varejistas podem implantar uma RSSU local para reduzir a dependência da conectividade com a Internet ou a disponibilidade do Azure. Também é possível implantar registros de PDV onde o modo offline estiver ativado se houver um problema com o servidor ou rede local.

- **Dispositivos de hardware/periféricos** – Um aspecto importante de um sistema Retail POS é sua capacidade de usar periféricos de PDV, como impressoras, caixas registradoras e terminais de pagamento. Embora todas as opções disponíveis de PDV possam usar dispositivos periféricos, somente o MPOS para Windows pode suportá-las diretamente. Para todos os outros aplicativos, uma ou mais estações de hardware são necessárias. Embora essa abordagem adicione flexibilidade, componentes adicionais devem ser implantados, configurados e ter manutenção.
- **Requisitos do sistema** – Os requisitos do sistema para o aplicativo de PDV variam. Lembre-se de verificar as informações mais recentes antes de fazer sua escolha. Por exemplo, como o CPOS é executado em um navegador, ele oferece suporte a uma ampla variedade de sistemas operacionais. Para obter mais informações sobre os requisitos do sistema, consulte [Requisitos de sistema para implantações na nuvem](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/system-requirements).
- **Implantação e manutenção** – A complexidade dos requisitos de implantação e manutenção pode variar, dependendo das escolhas de aplicativos e implantação. Por exemplo, para uma implementação de CPOS hospedada em nuvem, não é necessário instalação e atualização em cada dispositivo. Portanto, essa abordagem reduz muito a complexidade e os custos. No entanto, se você implantar o MPOS em cada registro e habilitar o modo offline, e também implantar estações de hardware compartilhadas, aumentará muito o número de pontos de extremidade que devem ser gerenciados.


[!INCLUDE[footer-include](../includes/footer-banner.md)]