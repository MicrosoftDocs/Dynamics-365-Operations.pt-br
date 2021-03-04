---
title: Criar, aprovar e assinar ofertas no Attract
description: Este tópico detalha como criar, aprovar e assinar uma oferta para um candidato usando o Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 02/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-19
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: dee545b6ca5d2791dea6609b4e1b25eba128f8b7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460291"
---
# <a name="create-approve-and-sign-offers-in-attract"></a>Criar, aprovar e assinar ofertas no Attract

[!include [banner](includes/banner.md)]

Em muitos casos, a preparação de um pacote de ofertas para um candidato precisa ser um processo muito rápido.
O uso dos modelos configurados pelo administrador do Attract reduzirá o tempo e o esforço para que os criadores de ofertas preparem e enviem ofertas para um candidato.

## <a name="create-an-offer"></a>Criar uma oferta

Quando o aplicativo Gerenciamento de ofertas é ativado, qualquer usuário com a função de gerente de contratação ou recrutador pode preparar um pacote de ofertas para o candidato. Para preparar a oferta, faça o seguinte:

1.  Navegue até o trabalho e a solicitação de emprego do candidato para o qual você está criando a oferta.

1.  Vá para **Estágio de oferta** e clique em **Preparar oferta**.

    Você será redirecionado para o aplicativo da oferta onde poderá ver o candidato com o status **Novo**. Você também pode ver outras ofertas com as quais está contribuindo, como criador ou aprovador.

1.  Clique em **Preparar Oferta**. 
    
    Você verá diferentes pacotes de ofertas que foram disponibilizados pelo administrador.

1.  Selecione um pacote e clique em **Concluído** para começar a preparar a oferta.

    O modelo de pacote da oferta é carregado com o trabalho correspondente e os detalhes do candidato são preenchidos na oferta.

1.  Todos os espaços reservados de dados da oferta que fazem parte do pacote da oferta ficam visíveis na página de aterrissagem. Você pode preencher todos os valores do pacote nesta página.

    Na página de aterrissagem, você também pode ver todos os modelos de documento que fazem parte do pacote da oferta.

1.  Agora você pode editar o conteúdo da oferta, dependendo de como o modelo foi configurado pelo administrador.

1.  Se você precisar remover documentos marcados como não obrigatórios, poderá fazer isso.

1. Quando todos os espaços reservados de dados da oferta forem preenchidos, clique em **Salvar** para salvar um rascunho da oferta.

>[!NOTE]
> Após um rascunho ser salvo, você pode excluir a versão de rascunho da oferta ou selecionar um novo modelo de pacote, se necessário.


## <a name="approve-an-offer"></a>Aprovar uma oferta

A maioria das ofertas precisam passar por um processo de aprovação para verificar se a oferta atende aos padrões necessários. Se uma oferta não atender a padrões, por exemplo, se o criador da oferta não seguiu as regras de dados da oferta e não substituiu os valores na oferta, o processo de aprovação será obrigatório. Para enviar uma oferta para aprovação, faça o seguinte.

1.  Quando a oferta estiver em estado de rascunho, adicione aprovadores no **Painel do aprovador**. 
    >[!NOTE]
    > Os gerentes de contratação são adicionados aprovadores por padrão. Você pode escolher qualquer usuário da organização como um aprovador da oferta.

1.  Se necessário, atribua aprovadores em um método de aprovação sequencial ou em um método de aprovação paralelo. Esta opção estará disponível apenas se tiver sido configurada como tal pelo administrador.
    >[!NOTE]
    > Se o processo de aprovação for sequencial, você poderá editar a sequência de aprovadores se necessário.

1.  Quando terminar de definir a cadeia de aprovação, você poderá editar o conteúdo do email de aprovação e enviar a notificação para os aprovadores. Clique em **Enviar para aprovadores**.
    >[!NOTE]
    > Se a oferta não era padrão, você precisa oferecer uma justificativa.

1.  Se o criador da oferta optar por ignorar um aprovador, eles poderão inserir uma nota e passar para o próximo aprovador.

Os aprovadores receberão um email solicitando que aprovem a oferta. Eles podem clicar no link no email para para abrir a oferta, analisar o pacote inteiro da oferta e aprová-lo ou devolvê-lo ao criador da oferta. Os aprovadores da oferta precisarão incluir uma observação adicional se estiverem rejeitando o pacote de ofertas para mais edições. 

Nos casos em que houver uma nova versão da oferta criada antes da ação do aprovador, ele não poderá aprovar ou rejeitar a oferta.

## <a name="offer-versioning"></a>Versões da oferta 

Quando a oferta for aprovada ou devolvida para mais edições, você poderá escolher a opção **Habilitar edição** para criar uma nova versão da oferta. A nova versão da oferta tem todos os valores de dados da oferta e a lista de aprovadores transferidos da última versão. 

Os aprovadores poderão alternar entre diferentes versões de ofertas se as versões forem compartilhadas com eles para aprovação. Além disso, um aprovador ou criador da oferta pode optar por excluir uma versão específica de rascunho da oferta para voltar ao estado anterior.


## <a name="send-an-offer-to-a-candidate"></a>Enviar uma oferta a um candidato 

Quando a oferta estiver salva, aprovada e pronta para ser enviada ao candidato, clique em **Enviar para candidato**.

Há várias medidas que você pode adotar antes de enviar a oferta ao candidato.
-  Você pode exibir a lista de documentos que fazem parte do pacote de ofertas que será enviado ao candidato.

-  Você pode especificar uma data de vencimento da oferta. Espera-se que os candidatos aceitem ou rejeitem a oferta antes da data de vencimento.  O candidato receberá um lembrete 48 horas antes do vencimento da oferta.

-  Talvez existam documentos adicionais a serem incluídos no processo de aceitação da oferta. Você terá a opção de listar o tipo de documento necessário.

- Opção de assinatura eletrônica: há duas maneiras de conectar o provedor de assinatura eletrônica de sua escolha. Vá para **Configurações de usuário** em **Oferta**, em **Conexões**, e conecte-se a **Adobe Sign** ou **DocuSign**. Como alternativa, você será solicitado a se conectar à página **Enviar a oferta para o candidato** se a conexão ainda não tiver sido estabelecida com base nas configurações do usuário. A conta de assinatura eletrônica só precisa ser conectada uma vez. A mesma licença de usuário é usada para todos os pacotes de oferta futuros que serão enviados pelo mesmo usuário. 

### <a name="adobe-sign"></a>Adobe Sign
Se o Adobe Sign foi escolhido como o método preferencial de assinatura eletrônica, os criadores de oferta precisam conectar a licença do Adobe Sign nesta etapa. 

### <a name="docusign"></a>DocuSign
Se o DocuSign foi escolhido como o método preferencial de assinatura eletrônica, os criadores de oferta precisam conectar a licença do DocuSign. Depois de entrar, a conta padrão e as permissões associadas ao perfil do DocuSign do usuário são conectadas ao Talent: Attract. 

-  Você pode exibir e editar o modelo de email conforme necessário.

Quando a oferta estiver pronta e você clicar em **Enviar para candidato**, o candidato receberá um email avisando que uma oferta está aguardando revisão.

>[!NOTE]
> Se você estiver usando o Adobe Sign ou DocuSign e tiver um erro ao enviar a oferta para o candidato, tente desconectar e reconectar a conta de usuário da assinatura eletrônica de **Configurações de usuário**. Se o problema persistir, entre em contato com nosso suporte usando o link **Relatar um problema**.

## <a name="candidates-actions-after-receiving-an-offer"></a>Ações do candidato após receber uma oferta

Após o candidato ser notificado de que uma oferta foi compartilhada com ele, poderá clicar no link no email para acessar o painel do aplicativo e exibir a oferta. O painel mostrará ao candidato as atividades a serem concluídas.

1.  Para exibir a oferta e todos os documentos relacionados, o candidato deve clicar em **Exibir oferta**.

    Os candidatos também podem baixar o pacote de ofertas em formato .zip.

1.  Para aceitar a oferta, os candidatos devem clicar em **Ir para a assinatura** para cada documento que faz parte do pacote de ofertas.

1.  Quando todos os documentos assinados individualmente forem aceitos, o candidato deverá optar por concluir o processo de aceitação clicando em **Aceitar Oferta** na parte superior da página.

1.  Para recusar a oferta, o candidato deverá clicar em **Recusar a oferta** na parte superior da página, selecionar um motivo apropriado, adicionar um comentário conforme necessário e clicar em **Recusar**.

1.  Após aceitar ou recusar a oferta, o candidato pode permanecer na exibição da oferta ou voltar ao painel do aplicativo.

1.  Se houver outros documentos solicitados como parte do processo de aceitação da oferta, o candidato deverá optar por carregar os documentos conforme necessário e marcá-los com o tipo de documento solicitado.

1.  O criador da oferta será notificado quando todos os documentos forem carregados e o pacote de ofertas for assinado.


## <a name="withdrawing-an-offer"></a>Retirada de uma oferta

Uma oferta pode ser retirada de um candidato a qualquer momento por várias motivos. 
1.  Retire a oferta clicando no botão de reticências (**…**) e, depois, em **Retirar a oferta**. 

2. Aparecerá uma mensagem perguntando se o candidato foi contactado sobre a alteração de status. Se o candidato ainda não tiver sido contactado, você poderá enviar um email a ele informando sobre outras ações. 

   A oferta não poderá mais ser acessada pelo candidato.


## <a name="closing-an-offer"></a>Fechamento de uma oferta 

Quando uma oferta é aceita, recusada ou retirada sem ações adicionais necessárias, você pode fechar a oferta para que não sejam feitas outras edições nesse pacote de ofertas.


[!INCLUDE[footer-include](../includes/footer-banner.md)]