---
title: Erro no caminho de certificação ao configurar a conexão de aplicativo
description: Se o aplicativo Warehouse Management mostrar o erro "Âncora de confiança para o caminho de certificação não encontrada", use esta página para aplicar uma solução alternativa ou resolver o problema.
author: ivanv-microsoft
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: WMA
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e4a36874ac4982c9c92a7dcc17c13c7c7c02bf8c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475583"
---
# <a name="trust-anchor-for-certification-path-not-found-when-setting-up-app-connection"></a>Âncora de confiança para o caminho de certificação não encontrada ao configurar conexão de aplicativo

## <a name="symptoms"></a>Sintomas

Ao tentar se conectar ao Supply Chain Management, o aplicativo Warehouse Management pode mostrar a seguinte mensagem de erro:

> java.security.cert.certPathValidatorException: Âncora de confiança para caminho de certificação não encontrada.

Esse problema pode afetar os dispositivos com as seguintes propriedades:

- **Versão do sistema operacional** : Android 4.4.x (como Zebra TC55). Isso não é um problema nas versões recentes do Android.
- **Local do Supply Chain Management**: nuvem
- **Modo de conexão**: segredo de cliente ou certificado

## <a name="possible-cause"></a>Possível causa

Talvez a Microsoft tenha atualizado os certificados de servidor SSL usados pelo Supply Chain Management. Como resultado, o certificado raiz e/ou um dos certificados intermediários podem ter sido alterados. Portanto, o novo certificado não está na lista de certificados de sistema confiáveis para o dispositivo móvel. As versões mais recentes do Android atualizam automaticamente as listas de certificados confiáveis, mas o Android 4.4.x não.

## <a name="resolution"></a>Resolução

Para resolver esse problema, siga uma destas etapas:

- Use a solução alternativa descrita na próxima seção para atualizar cada dispositivo relevante.
- *Talvez* seja possível contatar o Zebra ou o Google para obter uma atualização dos certificados de autoridade de certificação (CA) confiáveis do sistema. No entanto, não confirmamos isso.
- Se possível, pense em substituir dispositivos antigos por dispositivos que executem uma versão mais recente do Android (onde os certificados de autoridade de certificação confiáveis são atualizados automaticamente).

### <a name="workaround"></a>Solução alternativa

#### <a name="step-1-export-the-new-root-certificate-from-supply-chain-management"></a>Etapa 1: exportar o novo certificado raiz do Supply Chain Management

Para baixar manualmente o novo certificado raiz usando seu navegador de Internet, faça o seguinte:

1. Faça login no Supply Chain Management do Dynamics e abra a página inicial.

1. Na barra de endereços do navegador, selecione o ícone de cadeado para abrir a caixa de diálogo **O local é seguro**.
1. Na caixa de diálogo, selecione **Certificado (válido)** para abrir a janela **Certificado**.
1. Abra a guia **Caminho de certificação** da janela **Certificado**.
1. Selecione o primeiro certificado mostrado na hierarquia. (é o certificado raiz).
1. Abra a guia **Detalhes** da janela **Certificado**.
1. Selecione o botão **Copiar para arquivo** na parte inferior da guia **Detalhes**.
1. O **Assistente para exportação de certificados** é aberto. Selecione **Avançar** para continuar.
1. A página **Formato do arquivo de exportação** é aberta. Selecione **X.509 binário codificado por DER (.CER)**. Em seguida, selecione **Avançar** para continuar.
1. A página **Arquivos a serem exportados** será aberta; especifique um nome de arquivo e local. Em seguida, selecione **Avançar** para continuar.
1. A página **Concluindo o assistente para exportação de certificados** é aberta, mostrando o resultado da exportação. Selecione **Concluir**.

#### <a name="step-2-install-the-downloaded-certificate-onto-the-affected-devices"></a>Etapa 2: instalar o certificado baixado nos dispositivos afetados

Para instalar o certificado baixado, faça o seguinte:

1. Transfira o certificado baixado na etapa anterior para o dispositivo que você deseja atualizar. Por exemplo, você pode usar um cartão SD ou uma conexão de rede a fim de disponibilizar o arquivo para o dispositivo.
1. Abra as configurações de segurança do dispositivo e escolha a opção de menu para instalar um certificado a partir de um arquivo. (As etapas exatas para isso variam de acordo com o dispositivo e a versão do sistema operacional.)
1. O novo certificado deverá agora ser mostrado na guia **Usuário** para certificados confiáveis.
1. Repita esse procedimento para cada dispositivo afetado.
