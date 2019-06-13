<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="environment-reprovision.md" target-language="pt-BR">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>environment-reprovision.33170a.795ff0c91f6e5c2ac83dd610a125d2f6fdbbec70.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>795ff0c91f6e5c2ac83dd610a125d2f6fdbbec70</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/15/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\includes\environment-reprovision.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101">
          <source>When copying a database between environments, you will need to run the environment re-provisioning tool before the copied database is fully functional, to ensure that all Retail components are up-to-date.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ao copiar um banco de dados entre ambientes, você precisará executar a ferramenta de reprovisionamento de ambiente para que o banco de dados copiado fique totalmente funcional, para garantir que todos os componentes do Retail estejam atualizados.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102">
          <source>We recommend that you run this procedure whether you are using Retail components or not, because Retail functionality is included in all environments.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Recomendamos que você execute esse procedimento mesmo que não esteja usando vários componentes do Retail, porque a funcionalidade do Retail é incluída em todos os ambientes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Before you continue, you must make sure that the following prerequisites are met:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Antes de prosseguir, você deve verificar se os seguintes pré-requisitos são atendidos:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>If you are upgrading to the July 2017 release (also known as 7.2) 7.2.11792.56024, apply the following application X++ hotfixes in the destination environment before running the data upgrade in that environment.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se você estiver fazendo upgrade para a versão de julho de 2017 (também conhecida como 7.2) 7.2.11792.56024, aplique os hotfixes X++ de aplicativo a seguir no ambiente de destino antes de executar o upgrade de dados no ambiente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>These will prevent various errors occurring during the data upgrade:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Isso evitará que vários erros ocorram durante o upgrade de dados:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>KB 4036156 - Retail minor version upgrade - 'Variant number sequence is not set.'</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">KB 4036156 - upgrade secundário de versão do Retail - "A sequência de números da grade não está definida".</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>This fix package also includes KB 4035399 and KB 4035751.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Este pacote de correção também inclui o KB 4035399 e KB 4035751.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Note that you must have a minimum of Platform Update 9 to use this package.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Você deve possuir, pelo menos, o Platform Update 9 para usar este pacote.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>If you are unsure, install the latest binaries.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se você não tem certeza, instale os binários mais recentes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>If you are upgrading from Microsoft Dynamics AX 2012, install the following application X++ fixes in the destination environment before you run the data upgrade:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se você estiver atualizando do Microsoft Dynamics AX 2012, instale estas correções X++ de aplicativo no ambiente de destino antes de executar o upgrade de dados:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>KB 4033183 - Dynamics AX 2012 R2 or Dynamics AX 2012 R3 Pre-CU8 non-retail upgrade fails with Object not found for dbo.RETAILTILLLAYOUTZONE.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">KB 4033183 - O upgrade não varejo do Dynamics AX 2012 R2 ou Dynamics AX 2012 R3 Pre-CU8 falha e exibe a mensagem "Objeto não encontrado para dbo.RETAILTILLLAYOUTZONE.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>KB 4040692 - Dynamics AX 2012 R3 to Microsoft Dynamics 365 for Operations 7.2 upgrade fails on RetailSalesLine duplicate index on SalesLineIdx.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">KB 4040692 - O upgrade do Dynamics AX 2012 R3 para o Microsoft Dynamics 365 for Operations 7.2 falha no índice duplicado RetailSalesLine no SalesLineIdx.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>KB 4035490 - Performance issue with GeneralJournalAccountEntry MainAccount field upgrade script.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">KB 4035490 - Problema de desempenho com o script de upgrade do campo GeneralJournalAccountEntry MainAccount.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Follow these steps to run the Environment reprovisioning tool.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Siga estas etapas para executar a ferramenta de reprovisionamento de ambiente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>In the Shared asset library, select <bpt id="p1">**</bpt>Software deployable package<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na biblioteca de ativos compartilhados, selecione <bpt id="p1">**</bpt>Pacote de software implantável<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Download the Environment reprovisioning tool.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Baixe a ferramenta de reprovisionamento de ambiente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>In the asset library for your project, select <bpt id="p1">**</bpt>Software deployable package<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na biblioteca de ativos do seu projeto, selecione <bpt id="p1">**</bpt>Pacote de software implantável<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Select <bpt id="p1">**</bpt>New<ept id="p1">**</ept> to create a new package.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Selecione <bpt id="p1">**</bpt>Novo<ept id="p1">**</ept> para criar um novo pacote.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>Enter a name and description for the package.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Digite um nome e uma descrição para o pacote.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>You can use <bpt id="p1">**</bpt>Environment reprovisioning tool<ept id="p1">**</ept> as the package name.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Você pode usar <bpt id="p1">**</bpt>Ferramenta de reprovisionamento de ambiente<ept id="p1">**</ept> como o nome do pacote.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>Upload the package that you downloaded earlier.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Carregue o pacote baixado anteriormente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>On the <bpt id="p1">**</bpt>Environment details<ept id="p1">**</ept> page for your target environment, select <bpt id="p2">**</bpt>Maintain<ept id="p2">**</ept><ph id="ph1"> &gt; </ph><bpt id="p3">**</bpt>Apply updates<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na página <bpt id="p1">**</bpt>Detalhes de ambiente<ept id="p1">**</ept> do ambiente de destino, selecione <bpt id="p2">**</bpt>Manter<ept id="p2">**</ept><ph id="ph1"> &gt; </ph><bpt id="p3">**</bpt>Aplicar atualizações<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Select the Environment reprovisioning tool that you uploaded earlier, and then select <bpt id="p1">**</bpt>Apply<ept id="p1">**</ept> to apply the package.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Selecione a ferramenta de reprovisionamento de ambiente carregada anteriormente e selecione <bpt id="p1">**</bpt>Aplicar<ept id="p1">**</ept> para aplicar o pacote.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Monitor the progress of the package deployment.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Monitore o progresso da implantação do pacote.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>For more information about how to apply a deployable package, see <bpt id="p1">[</bpt>Apply a deployable package<ept id="p1">](../deployment/create-apply-deployable-package.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para obter mais informações sobre como aplicar um pacote implantável, consulte <bpt id="p1">[</bpt>Aplicar um pacote implantável<ept id="p1">](../deployment/create-apply-deployable-package.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>For more information about how to manually apply a deployable package, see <bpt id="p1">[</bpt>Install a deployable package<ept id="p1">](../deployment/install-deployable-package.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para obter mais informações sobre como aplicar um pacote implantável manualmente, consulte <bpt id="p1">[</bpt>Instalar um pacote implantável<ept id="p1">](../deployment/install-deployable-package.md)</ept>.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>