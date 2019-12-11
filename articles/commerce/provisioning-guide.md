---
title: Configurar um ambiente de avaliação de comércio eletrônico
description: Esta guia fornece instruções passo a passo para provisionar e configurar o ambiente de Visualização do Microsoft Dynamics 365 Commerce .
author: v-chgri
manager: annbe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b0dce2796e69cd8dee87cba176a521c26c81eb1a
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771671"
---
# <a name="configure-an-e-commerce-evaluation-environment"></a>Configurar um ambiente de avaliação de comércio eletrônico

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Esta guia fornece instruções passo a passo para provisionar e configurar o ambiente de Visualização do Microsoft Dynamics 365 Commerce . Antes de começar, recomendamos que você pelo menos olhe a documentação para ter uma ideia do que o processo implica e do que o guia contém.

*Observação: Se ainda não tiver acesso à Visualização do Microsoft Dynamics 365 Commerce, solicite acesso de visualização do [Site de comércio](https://aka.ms/Dynamics365CommerceWebsite).*

## <a name="summary"></a>Resumo
Para provisionar o ambiente com êxito, o projeto precisa ser criado com um nome e tipo de produto específico. O ambiente e o Retail Cloud Scale Unit também têm alguns parâmetros específicos que você precisará usar para iniciar o provisionamento de comércio eletrônico posteriormente. As instruções deste guia contêm todas as etapas necessárias que você precisará executar e os parâmetros você precisará usar.

Após o provisionamento bem-sucedido, há etapas algumas de pós-provisionamento que você precisa executar para preparar o ambiente de Visualização. Algumas etapas são opcionais, dependendo de quais aspectos do sistema você deseja avaliar. Depois, se você mudar de ideia, sempre poderá executar as etapas opcionais posteriormente.

Se tiver dúvidas sobre as etapas de provisionamento ou detectar problemas, avise-nos em [Visualização do Microsoft Dynamics 365 Commerce - grupo do Yammer](https://aka.ms/Dynamics365CommercePreviewYammer). 

## <a name="prerequisites"></a>Pré-requisitos
Estes são os pré-requisitos para provisionar seu ambiente de Visualização do Dynamics 365:
* Você tem acesso ao **portal do Lifecycle Services (LCS)**
* Você foi **aceito no programa de Visualização do Dynamics 365 Commerce**
* Você tem as permissões necessárias para criar um projeto para **Pré-venda de clientes potenciais** ou **Migrar, criar soluções e conhecer**
* Você é membro da função **Gerente de ambiente** ou **Proprietário do Projeto** no projeto no qual você estará provisionando o ambiente
* Você tem acesso de administrador à sua assinatura do Azure ou entra em contato com um administrador de assinatura que pode executar as duas etapas que exigem permissões de administrador em seu nome
* Você tem sua **ID de locatário do AAD** disponível
* Você criou um **Grupo de Segurança do AAD** a ser usado como **Grupo de administradores do sistema de Comércio eletrônico** e tem sua ID disponível
* Você criou um **upo de Segurança do AAD** a ser usado como **grupo moderador de Classificações e Opiniões** e tem sua ID disponível (pode ser o mesmo SG do grupo de administradores do sistema acima)
## <a name="provisioning-preview-environment"></a>Provisionando o ambiente de visualização
Essas instruções abrangem o provisionamento de um ambiente de Visualização do Microsoft Dynamics 365 Commerce . Depois de concluir com êxito essas etapas, você terá um ambiente de Visualização pronto para ser configurado. Todas as atividades descritas aqui ocorrem no portal do LCS.

*Observe que o acesso à visualização está vinculado à conta e à organização de LCS especificadas em seu aplicativo de visualização. Você precisa usar a mesma conta para provisionamento. Se você precisar usar uma conta ou locatário de LCS diferente para o ambiente de Visualização, precisará fornecer esses detalhes. Para informações de contato, consulte os "Recursos adicionais" abaixo*
### <a name="before-starting"></a>Antes de começar
##### <a name="grant-access-to-e-commerce-applications"></a>Conceder acesso aos aplicativos de comércio eletrônico

*Observação: **A pessoa que fez logon precisa ser administrador do locatário de DAA**. Sem concluir esta etapa com êxito, o restante das etapas do provisionamento falhará.*

1. Para esta etapa, você precisará de sua **ID de locatário do AAD**. É necessário autorizar os aplicativos de comércio eletrônico para acessar sua assinatura do Azure. A maneira mais fácil de realizar isso é montar um URL como este:

https://login.windows.net/{AAD_TENANT_ID}/oauth2/authorize?client_id=fbcbf727-cd18-4422-a723-f8274075331a&response_type=code&redirect_uri=https://sb.manage.commerce.dynamics.com/_commerce/Consent&response_mode=query&prompt=admin_consent&state=12345

2. **Não clique na URL diretamente**, em vez disso, copie e cole-a em seu navegador ou editor de texto e substitua **\{AAD_TENANT_ID\}** por sua **ID de locatário do AAD**, antes de navegar para a URL.
3. Você será apresentado à caixa de diálogo de logon do Microsoft AAD, na qual confirmará que quer conceder acesso do "Dynamics 365 Commerce (Versão prévia)" à sua assinatura.
4. Você irá para uma página que confirma se a operação foi bem-sucedida.

##### <a name="log-in-to-the-lcs"></a>Entre no LCS
1. Entre no portal de LCS: https://lcs.dynamics.com
1. Verifique se você está conectado com a mesma conta LCS usada para solicitar acesso à Visualização.
##### <a name="confirm-that-preview-features-are-available-and-enabled"></a>Confirme se os recursos de exibição estão disponíveis e habilitados
1. Na página inicial do LCS, role para a direita e clique no bloco **Gerenciamento de recursos de visualização**.
1. Role para baixo até "RECURSOS PRIVADOS DE VISUALIZAÇÃO" e verifique se os seguintes recursos estão disponíveis e habilitados:
    1. **Avaliação de Comércio eletrônico**
    1. **Ambientes do Programa de Visualização do Comércio**
1. Se você não conseguir ver esses recursos na lista, entre em contato conosco com seu email comercial, conta LCS e detalhes do locatário. Consulte **Recursos adicionais** abaixo para obter informações sobre como entrar em contato conosco.

![Bloco de gerenciamento de visualização](./media/preview1.png)

![Recursos de visualização](./media/preview2.png)
### <a name="create-project"></a>Criar Projeto
##### <a name="creating-new-project"></a>Criando um novo projeto
1. Clique em **+** para criar um novo projeto.
1. Se você for um parceiro, escolha **Migrar, criar soluções e conhecer**.
1. Se for cliente, escolha **Pré-vendas de clientes potenciais**.
1. Digite um nome, descrição e setor, como achar melhor.
1. Para **Nome do produto**, selecione **Dynamics 365 Retail**.
1. Para **Versão do produto**, selecione **Dynamics 365 Retail**.
1. Para **Metodologia**, selecione **Metodologia de implementação do Dynamics Retail**.
1. Você pode importar funções e usuários de um projeto existente, caso seja necessário.
1. Clique em **Criar**.
1. Você é enviado para a visualização do projeto.
##### <a name="add-azure-connector"></a>Adicione o Conector do Azure
1. Se for um parceiro, clique em **Configurações do projeto** dos blocos de ferramentas na extremidade direita.
1. Se for um cliente, escolha **Configurações do projeto** no menu superior.
1. Selecione **Conectores do Azure**.
1. Clique em **+ Adicionar** para adicionar o Conector do Azure.
1. Insira um nome.
1. Digite sua **ID da Assinatura do Azure**.
1. Habilite **Configurar para usar o Gerente de Recursos do Azure (ARM)**.
1. Verifique se o **Domínio (ou ID) de locatário do AAD de assinatura do Azure** está correto. Consulte seu administrador de assinatura do Azure, se necessário.
1. Clique em **Avançar**.
1. Siga as instruções na tela para conceder aos aplicativos necessários o acesso à sua assinatura. Consulte seu administrador de assinatura do Azure, se necessário:
    1. Entre no portal do Azure: https://portal.azure.com/
    1. Verifique se você escolheu o diretório correto.
    1. Clique em **Assinaturas** no menu à esquerda.
    1. Localize a assinatura correta da lista e selecione-a. Use a pesquisa, se necessário.
    1. Escolha **Controle de acesso (IAM)** no menu.
    1. Clique em **Adicionar** em **Adicionar uma atribuição da função** no lado direito. O painel **Adicionar atribuição da função** é aberto.
    1. Para **Função**, selecione **Colaborador**.
    1. Para **Atribuir acesso a**, deixe como **Usuário, grupo ou serviço principal do Azure AD**.
    1. Em **Selecionar**, insira **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.
    1. Selecione **Serviços de Implantação do Dynamics [wsfed-habilitado]** da lista.
    1. Clique em **Salvar**.
1. Clique em **Avançar**.
1. Siga as instruções na tela para conceder aos aplicativos necessários o acesso à sua assinatura. Consulte seu administrador de assinatura do Azure, se necessário.
1. Clique em **Avançar**.
1. Para **Região do Azure**, escolha **Leste do EUA**, **Leste dos EUA 2**, **Oeste dos EUA** oU **Oeste dos EUA 2**.
1. Clique em **Conectar**.
1. Seu Conector do Azure deverá aparecer na lista.
### <a name="import-extension"></a>Extensão da Importação
1. Volte para a página inicial do seu projeto clicando no nome do projeto na parte superior.
1. Se for um parceiro, clique em **Biblioteca de ativos** dos blocos de ferramentas na extremidade direita.
1. Se for um cliente, escolha **Biblioteca de ativos** no menu superior.
1. Selecione **Pacote de software implantável** na lista à esquerda.
1. Clique em **IMPORTAR** no painel de ação.
1. Selecione **Extensão da Demonstração da Versão Prévia do Comércio** da lista de ativos na **BIBLIOTECA DE ATIVOS COMPARTILHADOS**.
1. Clique em **Retirar**.
1. Você retornará à biblioteca de Ativos e deverá ver a extensão na lista.

![Criação do projeto - versões](./media/import.png)
### <a name="deploy-environment"></a>Implantar ambiente

*Observação: é possível que as etapas 6, 7 e / ou 8 não sejam exibidas, pois as telas com opção única são ignoradas. Quando você estiver na visualização**Parâmetros do ambiente**, confirme se tem o texto "Dynamics 365 Commerce (Versão prévia) - Demonstração (10.0.6 com atualização de Plataforma 30)" diretamente acima do campo **Nome do ambiente**. Consulte a captura de tela abaixo.*

1. No menu superior, selecione **Ambientes hospedados na nuvem**.
1. Clique em **+ Adicionar** para adicionar um ambiente.
1. Para **Versão do aplicativo**, selecione **10.0.6**.
1. Para **Versão da plataforma**, selecione **Atualização da Plataforma 30**.
1. Clique em **Avançar**.
1. Para a topologia de ambiente, escolha **DEMONSTRAÇÃO**.
1. Para a topologia de ambiente, escolha **Dynamics 365 Commerce (Versão Prévia) - Demonstração**.
1. Se você configurou um único Conector do Azure anteriormente, isso será usado para este ambiente. Se você configurou vários Conectores do Azure, tem a opção de selecionar qual conector você gostaria de usar: **Leste dos EUA**, **Leste dos EUA 2**, **Oeste dos EUA** ou **Oeste dos EUA 2** (recomendado para melhor desempenho ponta a ponta)
1. Insira um **Nome do ambiente**.
1. Ajuste o tamanho da VM como achar melhor. (É recomendado VM SKU **D13 v2**.)
1. Deixe as **Configurações avançadas** como estão.
1. Depois de revisar os preços e os termos de licenciamento na tela, marque a caixa para indicar o contrato.
1. Clique em **Avançar**.
1. Na tela de confirmação da implantação, depois de verificar se os detalhes estão corretos, clique em **Implantar**.
1. Você voltará à visualização **Ambientes hospedados na nuvem** e seu ambiente deverá aparecer na lista.
1. Seu ambiente solicitado será exibido na fila e, em seguida, implantado. Levará algum tempo para que todos os fluxos de trabalho do ambiente sejam concluídos. Verifique novamente após algumas horas (aproximadamente de 6 a 9 horas).
1. Antes de continuar, verifique se o status de ambiente está **Implantado**.

![Criação do projeto - versões](./media/project1.png)

![Criação do projeto - topologia 1](./media/project2.png)

![Criação do projeto - topologia 2](./media/project3.png)

![Criação do projeto - parâmetros de ambiente](./media/project4.png)
### <a name="initialize-rcsu"></a>Inicialize o RCSU
1. Enquanto estiver na visualização **Ambientes hospedados na nuvem** selecione seu ambiente da lista.
1. Na visualização do ambiente, no lado direito da tela, clique em **Detalhes completos**. A visualização de detalhes do ambiente será exibida.
1. Em **RECURSOS DO AMBIENTE**, clique em **Gerenciar**.
1. Na guia **Varejo** , clique em **Inicialize**. A visualização dos parâmetros de inicialização do RCSU será exibida.
1. Para **REGIÃO**, selecione **Leste dos EUA**, **Leste dos EUA 2**, **Oeste dos EUA** ou **Oeste dos EUA 2**.
1. Para **VERSÃO**, primeiro selecione **Especificar uma versão** da lista suspensa, depois especifique **9.16.19262.5** no campo de texto que aparece abaixo. *Observação: Certifique-se de **especificar a versão exata** listada aqui para não ter que atualizar a RCSU posteriormente para a versão correta.*
1. Habilitar **Aplicar extensão**.
1. Da lista de extensões, escolha **Extensão da Demonstração da Versão Prévia do Comércio**.
1. Clique em **Inicializar**.
1. Na tela de confirmação da implantação, depois de verificar se os detalhes estão corretos, clique em **Sim**.
1. Você retornará à visualização **Gerenciamento de varejo** com a guia **Varejo** ativada. Sua RCSU foi enfileirada para provisionamento.
1. Aguarde até que seu status de RCSU seja **ÊXITO** antes de continuar (levará aproximadamente 2-5 horas).
### <a name="initialize-e-commerce"></a>Inicializar comércio eletrônico
1. Alterne para a guia **Comércio eletrônico (Versão prévia)**.
1. Após revisar o consentimento da Visualização, clique em **Configurar**.
1. Digite nome para **Nome do locatário de comércio eletrônico**. No entanto, observe que isso estará visível em algumas das URLs que apontam para sua instância de comércio eletrônico.
1. Para **Nome da Retail cloud scale unit**, selecione sua RCSU da lista (a lista deverá ter somente uma opção).
1. **Geografia de comércio eletrônico** é preenchida automaticamente e não pode ser alterada.
1. Clique em **Avançar** para continuar.
1. Para **Nomes de host suportados**, insira qualquer domínio válido (por exemplo, www.fabrikam.com).
1. Para **Grupo de segurança do AAD para o administrador do sistema**, insira o ID de SG de AAD para usar como o grupo de administradores do sistema de comércio eletrônico.
1. Para **Grupo de segurança do AAD para o moderador de opinião e de avaliações**, insira a ID de SG de DAA que deseja usar como grupo de moderadores de Classificações e Opiniões.
1. Deixe os valores **B2C** vazios (7 campos que começam com B2C).
1. Deixe a opção **Habilitar classificações e examinar o serviço** habilitada.
1. Clique em **Inicializar**.
1. Você retornará à visualização **Gerenciamento de varejo** com a guia **Comércio eletrônico (Versão prévia)** ativada. Sua inicialização de Comércio eletrônico começou.
1. Antes de continuar, aguarde até que o status de inicialização do seu comércio eletrônico seja **INICIALIZAÇÃO COM ÊXITO**.
1. Em **LINKS** na parte inferior direita.
    * Anote o link **site de comércio eletrônico**. Este é o link para a raiz de seu site C2.
    * Anote o link **Ferramenta de gerenciamento de site de comércio eletrônico**. Este é o link para a ferramenta de gerenciamento de sites (ferramenta de criação de C1).
## <a name="post-provisioning-steps"></a>Etapas pós-provisionamento
Nesse estágio, o ambiente foi provisionado de ponta a ponta, mas ainda há etapas de configuração que precisam ser observadas antes que você possa começar a avaliar o ambiente.
### <a name="before-starting"></a>Antes de começar
1. No menu superior, selecione **Ambientes hospedados na nuvem**.
1. Selecione seu ambiente na lista.
1. Clique em **Detalhes completos** nas informações sobre o ambiente à direita.
1. Clique em **Logon** para abrir um menu, escolha **Fazer logon no ambiente**.

Verifique se a entidade legal **USRT** está selecionada (canto superior direito).

### <a name="configure-pos"></a>Configurar POS
##### <a name="associate-worker-with-your-identity"></a>Associar o trabalhador com sua identidade
1. Usando o menu à esquerda, vá para **Módulos > Varejo > Funcionários > Trabalhadores**.
1. Na lista, localize e selecione o registro **000713 - Andrew Collette**.
1. No Painel de Ação, clique em **Varejo**.
1. Clique em **Associar identidade existente**.
1. No campo **Email** (à direita de **Pesquisar usando email**), digite seu endereço de email.
1. Clique em **Pesquisar**.
1. Selecione o registro com seu nome.
1. Clique em **OK**.
1. Clique em **Salvar**.
##### <a name="activate-cloud-pos"></a>Ativar PDV em nuvem
1. Entre no portal de LCS.
1. Navegue até seu projeto.
1. No menu superior, selecione **Ambientes hospedados na nuvem**.
1. Selecione seu ambiente na lista.
1. Clique em **Detalhes completos** nas informações sobre o ambiente à direita.
1. Clique em **Logon** para abrir um menu, escolha **Faça Logon no Ponto de Venda da Nuvem**, o PDV deverá ser carregado.
1. Clique em **Avançar**.
1. Faça logon com sua conta AAD.
1. Em **Nome da loja**, escolha **São Francisco**.
1. Clique em **Avançar**.
1. Em **Registro e dispositivo**, escolha **SANFRAN-1**.
1. Clique em **Ativar**.
1. Você deve sair e terminar na tela de logon do PDV.
1. Agora você pode fazer logon na experiência do Cloud POS usando o ID do operador **000713** e a senha **123**.
### <a name="site-setup"></a>Configuração do site
1. Faça logon na **ferramenta de gerenciamento de site** usando a URL anotada anteriormente.
1. Clique no site **Fabrikam** para abrir a caixa de diálogo de configuração do site.
1. Para domínio, selecione o domínio digitado anteriormente ao inicializar o comércio eletrônico.
1. Para o canal padrão, selecione **Loja online estendida Fabrikam**. *Observação: Certifique-se de selecionar a loja online **estendida***
1. Para o idioma padrão, selecione **en-us**.
1. Deixe **Path** como está.
1. Clique em **OK**.
1. Você irá para a lista de páginas do site.
### <a name="enable-jobs"></a>Habilitar trabalhos
1. Faça logon no ambiente (Matriz).
1. Usando o menu à esquerda, vá para **Varejo > Consultas e relatórios > Trabalhos em lotes**.
1. Execute as seguintes etapas para cada um dos trabalhos na lista abaixo:
    * **Processar notificação por email de pedido de varejo**.
    * **Disponibilidade do produto**.
    * **P-0001**.
    * **Sincronizar trabalho de ordens**.
1. Use o Filtro Rápido para procurar o trabalho usando seu nome (listado acima).
1. Se o Status do trabalho for **Retido**, execute as seguintes etapas:
    1. Selecione o registro.
    1. Do painel de ação, abra a faixa **Trabalho em lote** e clique em **Alterar status**.
    1. Selecione **Aguardando** e Clique em **OK**.
### <a name="run-full-data-sync"></a>Executar sincronização de dados completa
1. Usando o menu à esquerda, vá para **Módulos > Varejo > configuração da Sede > agendador do Retail > Banco de dados do canal**.
1. O canal **Padrão** é selecionado da lista à esquerda. *Selecione o outro canal disponível (chamado **scXXXXXXXXX**)*.
1. Clique **Sincronização de dados completa** do painel de ação.
1. Digite **9999** como a agenda de distribuição.
1. Clique em **OK**.
1. Clique em **OK**.
### <a name="after-these-steps-you-are-ready-to-start-evaluating-your-preview-environment"></a>Após essas etapas, você estará pronto para começar a avaliar seu ambiente de visualização!
Use a URL **Ferramenta de gerenciamento de site de comércio eletrônico** para navegar até a experiência de criação C1 e a URL **site de comércio eletrônico** para navegar até a experiência do site C2.

## <a name="additional-resources"></a>Recursos adicionais
### <a name="how-to-find-your-aad-tenant-id"></a>Como encontrar a ID do Locatário de AAD
A ID do Locatário de AAD é uma GUID e para com esta: **72f988bf-86f1-41af-91ab-2d7cd011db47**
##### <a name="from-azure-portal"></a>Do Portal do Azure
1. Entre no portal do Azure: https://portal.azure.com/
1. Verifique se você escolheu o diretório correto.
1. Clique em **Azure Active Directory** no menu à esquerda.
1. Escolha **Propriedades** em **Gerenciar**.
1. A ID do Locatário de AAD é mostrada em **ID do Diretório**.
##### <a name="from-openid-connect-metadata"></a>De metadados de Conexão de OpenID
Crie **URL de OpenID** substituindo **\{YOUR_DOMAIN\}** pelo seu domínio, por exemplo, microsoft.com: https://login.microsoftonline.com/{YOUR_DOMAIN}/.well-known/openid-configuration seria https://login.microsoftonline.com/microsoft.com/.well-known/openid-configuration

1. Navegue até **URL OpenID** com seu domínio.
1. A ID de locatário do AAD pode ser vista em vários valores da propriedade.
1. Localize **authorization_endpoint** e extraia o GUID direito após **login.microsoftonline.com/**.
### <a name="how-to-find-the-id-of-your-aad-security-group"></a>Como encontrar o ID do seu grupo de segurança de AAD
O ID do grupo de segurança AAD é um GUID e se parece com este exemplo: **436ea7f5-ee6c-40c1-9f08-825c5811066a**

Esta etapa pressupõe que o usuário seja um membro do grupo para o qual está tentando localizar a ID.
1. Navegue até o Graph Explorer: https://developer.microsoft.com/en-us/graph/graph-explorer#
1. Clique em **Entrar com a conta da Microsoft** e entre usando suas credenciais.
1. Após entrar, clique em **mostrar mais amostras** à esquerda.
1. Habilite **Grupos** no painel direito.
1. Feche o painel direito.
1. Clique em **todos os grupos aos quais eu pertenço**.
1. Localize seu grupo da caixa de texto **Visualização de Resposta**.
1. A ID do grupo de segurança é anotada na propriedade **id**.
### <a name="test-credit-card-information-to-perform-test-purchases"></a>Testar informações do cartão de crédito para executar testes de compra
Para executar transações de teste no site, você pode usar as informações do cartão de crédito de teste:

Número do cartão: 4111-1111-1111-1111, vencimento: 10/20, CVV: 737

*Observação: Você não deve tentar usar as informações reais do cartão de crédito no local do teste sob nenhuma circunstância!*
### <a name="useful-links"></a>Links úteis
* [LCS (Lifecycle services)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)
* [RCSU (Retail Cloud Scale Unit)](https://docs.microsoft.com/en-us/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)
* [Portal do Microsoft Azure](https://azure.microsoft.com/en-us/features/azure-portal)
* [Site do Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)
* [Recursos de ajuda do Dynamics 365 Retail](../retail/index.md)
### <a name="microsoft-dynamics-365-commerce-preview-support"></a>Suporte à visualização do Microsoft Dynamics 365 Commerce
Se você tiver problemas ao executar as etapas de provisionamento, visite [Visualização do Microsoft Dynamics 365 Commerce - grupo Yammer](https://aka.ms/Dynamics365CommercePreviewYammer) para obter ajuda. 

Se você estiver com problemas para acessar o grupo do Yammer, pode entrar em contato conosco por e-mail em **Dynamics365Commerce@microsoft.com**. Este endereço de email não é monitorado ativamente, portanto, espere um atraso na resposta.
***
## <a name="prerequisites-for-optional-features"></a>Pré-requisitos para recursos opcionais
Se quiser avaliar os recursos transacionais de email, os seguintes pré-requisitos deverão ser atendidos:
* Você tem um servidor de email disponível (servidor SMTP), que pode ser usado na assinatura do Azure na qual você provisiona o ambiente de visualização.
* Você tem o FQDN/IP do servidor, o número da porta SMTP e os detalhes de autenticação disponíveis.

Se você quiser avaliar os recursos do Gerenciamento de Ativos Digitais, ingerir especificamente novas imagens do omnicanal, os seguintes pré-requisitos deverão ser atendidos:
* É necessário ter seu **Nome do locatário de CMS** disponível. As instruções para localizar este nome estão abaixo.
### <a name="configure-image-backend-optional"></a>Configurar backend da imagem (opcional)
##### <a name="finding-your-media-base-url"></a>Localizando a URL base da Mídia
*Observação: Antes de concluir esta etapa, você deve concluir a **Configuração do Site**.*
1. Faça logon na ferramenta de gerenciamento de site usando a URL anotada anteriormente.
1. Abra o site **Fabrikam**.
1. Escolha **Ativos** no menu à esquerda.
1. Selecione qualquer ativo único da imagem.
1. Localize a **URL Pública** no inspetor de propriedade à direita. Ele tem uma URL.
    * Exemplo de URL: https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC
1. Substitua o último identificador no URL (MA1nQC no URL de exemplo acima) pela seguinte string: **search?fileName=**
    * Exemplo de URL após substituição: https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=
    * Este é seu **URL base da Mídia** - anote-o.
##### <a name="updating-the-media-base-url"></a>Atualização da URL base da Mídia
1. Faça logon no ambiente (Matriz).
1. Usando o menu à esquerda, vá para **Módulos > Varejo > Configuração do Canal > Perfis do canal**.
1. Clique em **Editar**.
1. Nas **Propriedades do perfil**, substitua o valor da propriedade da **URL Base do Servidor de Mídia** pela **URL Base de Mídia** que você criou anteriormente.
1. Selecione o outro canal da lista à esquerda, em canal **Padrão**.
1. Em **Propriedades de perfil**, clique em **+ Adicionar**.
1. Para a propriedade que foi adicionada, escolha **URL Base do Servidor de Mídia** como a chave da propriedade e para o valor da propriedade, insira a **URL base de Mídia** criada anteriormente.
1. Clique em **Salvar**.

### <a name="configure-email-server-optional"></a>Configurar o servidor de email (opcional)
Observe que o servidor SMTP ou o serviço de email digitado aqui deve estar acessível na assinatura do Azure que você está usando para o ambiente.
1. Faça logon no ambiente (Matriz).
1. Usando o menu à esquerda, vá para **Módulos > Varejo > Configuração da Sede > Parâmetros > Parâmetros de email**.
1. Clique na guia **Configurações de SMTP**.
1. No **campo do Servidor de saída de emails**, digite o FQDN o endereço IP de seu servidor SMTP ou serviço de email.
1. No campo **Número da porta de SMTP** , insira o número da porta (o padrão é a 25 para não usar SSL).
1. No campo **Nome do usuário** , digite um valor (se for solicitada a autenticação).
1. No campo **Senha** , digite um valor (se for solicitada a autenticação).
1. Clique em **Salvar**.
1. Clique em **Atualizar**.
1. Clique na guia **Email de teste**.
1. No campo Provedor de email, escolha **SMTP**.
1. No campo **Enviar a** , insira o endereço de email para o qual você quer que o email de teste seja enviado.
1. Clique em **Enviar email de teste**.
### <a name="configure-email-templates-optional"></a>Configurar modelos de email (opcional)
O modelo de email para cada evento transacional para o qual você deseja enviar emails precisa ser atualizado com um endereço de email do remetente válido.
1. Usando o menu à esquerda, vá para **Módulos > administração da Organização > Configuração > Modelos de email da organização**.
1. Clique em **Mostrar lista**.
1. Para cada um dos modelos na lista:
    1. No campo **Email do remetente** , digite o endereço de email do remetente para este modelo de email.
    1. (Opcional) No campo **Nome do remetente**, digite um nome que será usado como remetente para este modelo de email.
1. Clique em **Salvar**.
### <a name="customizing-email-templates-optional"></a>Personalizando modelos de email (opcional)
Convém personalizar os modelos de email para usar imagens diferentes ou atualizar os links no modelo para voltar ao seu ambiente de visualização. As etapas abaixo explicam como baixar os modelos padrão, personalizá-los e atualizar os modelos no sistema.
1. Usando um navegador, faça download do [arquivo templates.zip do email padrão de Visualização do Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) que contém os seguintes documentos HTML para seu computador local.
    1. Módulo de confirmação da ordem
    1. Emitir modelo de vale-presente
    1. Novo modelo de ordem
    1. Empacotar modelo de ordem
    1. Separar modelo de ordem
1. Personalizar os modelos usando um texto ou editor HTML. Consulte uma lista de tokens suportados abaixo.
1. Faça logon no ambiente (Matriz).
1. Usando o menu à esquerda, vá para **Módulos > Varejo > Configuração da Sede > Parâmetros > Modelos de email da organização**.
1. Expanda a lista à esquerda para consultar todos os modelos.
1. Para cada um dos modelos que você deseja personalizar, execute as seguintes etapas:
    1. Selecione o modelo da lista.
    1. Em **Conteúdo da mensagem de email**, selecione a versão do idioma apropriado da lista (padrão**pt-br**).
    1. Em **Conteúdo da mensagem de email**, clique em **Editar**, você deverá ver a abertura do painel **Carregar modelo de email**.
    1. Clique em **Procurar** e localize o arquivo HTML com o conteúdo personalizado.
    1. Clique em **Carregar**, o modelo será carregado no sistema e a visualização será mostrada.
    1. Clique em **OK**.
    1. (Opcional) Personalize a propriedade **Assunto** do modelo.
    1. Clique em **Salvar**.

#### <a name="supported-tokens-in-the-email-template"></a>Tokens suportados no modelo de email
Esses tokens serão substituídos no momento da renderização do email pelos valores reais que se aplicam ao cliente e seu pedido.

**Ordem de venda** - Os seguintes tokens se aplicam à ordem de venda geral.

|Nome do token|Token |
|---|---|
|Número da ordem|%salesid%|
|Nome do cliente|%customername%|
|Endereço de entrega|%deliveryaddress%|
|Endereço para cobrança|%customeraddress%|
|Data da ordem|%shipdate%|
|Modo de entrega|%modeofdelivery%|
|Desconto|%discount%|
|Imposto|%tax%|
|Total da ordem|%total%|

**Linha de venda** - Os seguintes tokens são preenchidos para cada produto no pedido.

*Observação: Coloque os tokens **Lista de produtos - início** e **Lista de produtos - fim** no início e no fim do bloco HTML que se repete para cada produto.*

|Nome do token|Token |
|---|---|
|Lista de produtos - início|\<!--%tablebegin.salesline% -->|
|Lista de produtos - fim|\<!--%tableend.salesline%-->|
|Nome do produto|%lineproductname%|
|Descrição|%lineproductdescription%|
|Quantidade|%linequantity%|
|Preço unitário da linha|%lineprice% (verificação)|
|total do item de linha|%linenetamount%|
|desconto de linha|%linediscount%|
|Data da remessa|%lineshipdate%|
|Método de aquisição|%linedeliverymode%|
|endereço de entrega|%linedeliveryaddress%|
|Unidade de venda da linha|%lineunit%|

