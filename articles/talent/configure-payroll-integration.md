---
title: Configurar a integração da folha de pagamento entre o Talent e o Dayforce
description: Este tópico explica como configurar a integração entre o Microsoft Dynamics 365 Talent e o Ceridian Dayforce para processar um ciclo de pagamento.
author: andreabichsel
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: ec1d14cb14ab709dfc1bead4be0785904efcce4e
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251030"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="96b69-103">Configurar a integração da folha de pagamento entre o Talent e o Dayforce</span><span class="sxs-lookup"><span data-stu-id="96b69-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="96b69-104">A integração entre o Microsoft Dynamics 365 Talent e o Ceridian Dayforce depende de várias etapas de configuração descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="96b69-104">The integration between Microsoft Dynamics 365 Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="96b69-105">Você deve configurar a integração no Talent e no Dayforce antes de poder processar uma execução de pagamento.</span><span class="sxs-lookup"><span data-stu-id="96b69-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="96b69-106">Ao usar um serviço como o Dayforce para concluir execuções de pagamento, é necessário ativar a integração no Talent.</span><span class="sxs-lookup"><span data-stu-id="96b69-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="96b69-107">A integração requer dados específicos do Talent.</span><span class="sxs-lookup"><span data-stu-id="96b69-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="96b69-108">Portanto, você deve verificar se os dados mapeados para o Dayforce estão configurados no Talent de forma compatível com a integração.</span><span class="sxs-lookup"><span data-stu-id="96b69-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="96b69-109">A integração usa as seguintes categorias amplas de dados:</span><span class="sxs-lookup"><span data-stu-id="96b69-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="96b69-110">Dados de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="96b69-110">Human resources data</span></span>
- <span data-ttu-id="96b69-111">Dados de remuneração</span><span class="sxs-lookup"><span data-stu-id="96b69-111">Compensation data</span></span>
- <span data-ttu-id="96b69-112">Dados da folha de pagamento, como ciclos de pagamento, períodos de pagamento e códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="96b69-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="96b69-113">Dados do trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-113">Worker data</span></span>

<span data-ttu-id="96b69-114">Este tópico descreve as etapas que você deve seguir para ativar a integração.</span><span class="sxs-lookup"><span data-stu-id="96b69-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="96b69-115">Também explica os tipos de dados e os detalhes de configuração que a integração requer.</span><span class="sxs-lookup"><span data-stu-id="96b69-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="96b69-116">Habilitar a integração</span><span class="sxs-lookup"><span data-stu-id="96b69-116">Enable the integration</span></span>

<span data-ttu-id="96b69-117">No Talent, você deve ativar a integração e inserir as informações de configuração para se conectar ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="96b69-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="96b69-118">Para que a transação de contabilidade produzida seja importada para o Microsoft Dynamics 365 Finance, também é preciso configurar uma conta de armazenamento do Microsoft Azure e inserir a cadeia de conexão do Armazenamento do Azure no Finance.</span><span class="sxs-lookup"><span data-stu-id="96b69-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="96b69-119">Para ativar a integração no Talent, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="96b69-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="96b69-120">Na página **Administração do sistema**, selecione **Configuração de integração**.</span><span class="sxs-lookup"><span data-stu-id="96b69-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="96b69-121">Digite o ponto de extremidade seguro do File Transfer Protocol (FTP) e o caminho seguro da pasta FTP.</span><span class="sxs-lookup"><span data-stu-id="96b69-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="96b69-122">Digite o nome e a senha do usuário que acessará o ponto de extremidade e o caminho da pasta seguros do FTP.</span><span class="sxs-lookup"><span data-stu-id="96b69-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="96b69-123">Teste a conexão, conforme necessário, e defina a opção **Habilitar integração da folha de pagamento** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="96b69-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="96b69-124">Quando a integração é ativada, o pacote e os arquivos de exportação de dados são criados e a frequência é configurada.</span><span class="sxs-lookup"><span data-stu-id="96b69-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="96b69-125">Você pode alterar essa frequência conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="96b69-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="96b69-126">Para obter mais informações sobre as contas de armazenamento do Azure e as cadeias de conexão do Armazenamento do Azure, consulte os seguintes tópicos do Azure:</span><span class="sxs-lookup"><span data-stu-id="96b69-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="96b69-127">Sobre as contas de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="96b69-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="96b69-128">Configurar cadeias de conexão do Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="96b69-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="96b69-129">Detalhes técnicos quando a integração da folha de pagamento está habilitada</span><span class="sxs-lookup"><span data-stu-id="96b69-129">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="96b69-130">A ativação da integração da folha de pagamento tem dois efeitos principais:</span><span class="sxs-lookup"><span data-stu-id="96b69-130">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="96b69-131">Um projeto de exportação de dados denominado "Exportação de integração da folha de pagamento" é criado.</span><span class="sxs-lookup"><span data-stu-id="96b69-131">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="96b69-132">Este projeto contém as entidades e os campos necessários para a integração da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="96b69-132">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="96b69-133">Para revisar o projeto, vá para **Administração do sistema**, selecione o bloco **Gerenciamento de dados** e abra o projeto de dados da lista de projetos.</span><span class="sxs-lookup"><span data-stu-id="96b69-133">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="96b69-134">Esse trabalho em lotes executa o projeto de exportação de dados, criptografa o pacote de dados resultante e transfere o arquivo do pacote de dados para a empresa de SFTP configurada na tela **Configuração de integração**.</span><span class="sxs-lookup"><span data-stu-id="96b69-134">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="96b69-135">O pacote de dados transferido para a empresa de SFTP é criptografado usando uma chave exclusiva para o pacote.</span><span class="sxs-lookup"><span data-stu-id="96b69-135">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="96b69-136">A chave é um Azure Key Vault acessível somente pelo Ceridian.</span><span class="sxs-lookup"><span data-stu-id="96b69-136">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="96b69-137">Não é possível descriptografar e revisar o conteúdo do pacote de dados.</span><span class="sxs-lookup"><span data-stu-id="96b69-137">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="96b69-138">Se você precisar examinar o conteúdo do pacote de dados, exporte manualmente o projeto de dados "Exportação de integração da folha de pagamento", baixe-o e abra-o</span><span class="sxs-lookup"><span data-stu-id="96b69-138">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="96b69-139">A exportação manual não aplicará a criptografia nem transferirá o pacote.</span><span class="sxs-lookup"><span data-stu-id="96b69-139">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="96b69-140">Configurar seus dados</span><span class="sxs-lookup"><span data-stu-id="96b69-140">Configure your data</span></span> 

<span data-ttu-id="96b69-141">Para processar a folha de pagamento, você deve configurar dados de RH no Talent.</span><span class="sxs-lookup"><span data-stu-id="96b69-141">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="96b69-142">Você deve configurar dados organizacionais, como cargos e posições, juntamente com informações sobre benefícios e remuneração.</span><span class="sxs-lookup"><span data-stu-id="96b69-142">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="96b69-143">Esses dados fornecem as informações de emprego, pagamento e dedução necessárias para gerar o pagamento do empregado.</span><span class="sxs-lookup"><span data-stu-id="96b69-143">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="96b69-144">Dados de RH</span><span class="sxs-lookup"><span data-stu-id="96b69-144">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="96b69-145">Benefícios</span><span class="sxs-lookup"><span data-stu-id="96b69-145">Benefits</span></span> 

<span data-ttu-id="96b69-146">O RH fornece ferramentas para a configuração e manutenção dos benefícios, deduções e planos de remuneração do trabalhador que uma organização oferece ou processa para seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="96b69-146">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="96b69-147">Ao criar benefícios, tenha em mente os dados e configurações a seguir usados no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="96b69-147">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="96b69-148">Planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="96b69-148">Benefit plans</span></span>

- <span data-ttu-id="96b69-149">Plano (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-149">Plan (required)</span></span>
- <span data-ttu-id="96b69-150">Tipo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-150">Type (required)</span></span>
- <span data-ttu-id="96b69-151">Impacto da folha de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-151">Payroll impact (required)</span></span>
- <span data-ttu-id="96b69-152">Recuperar atrasos de pagamento</span><span class="sxs-lookup"><span data-stu-id="96b69-152">Recover arrears</span></span>
- <span data-ttu-id="96b69-153">Método de dedução</span><span class="sxs-lookup"><span data-stu-id="96b69-153">Deduction method</span></span>
- <span data-ttu-id="96b69-154">Prioridade da dedução</span><span class="sxs-lookup"><span data-stu-id="96b69-154">Deduction priority</span></span>
- <span data-ttu-id="96b69-155">Limitar período</span><span class="sxs-lookup"><span data-stu-id="96b69-155">Limit period</span></span>
- <span data-ttu-id="96b69-156">Valor de limite</span><span class="sxs-lookup"><span data-stu-id="96b69-156">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="96b69-157">Benefícios</span><span class="sxs-lookup"><span data-stu-id="96b69-157">Benefits</span></span>

- <span data-ttu-id="96b69-158">Plano (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-158">Plan (required)</span></span>
- <span data-ttu-id="96b69-159">Tipo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-159">Type (required)</span></span>
- <span data-ttu-id="96b69-160">Opção (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-160">Option (required)</span></span>
- <span data-ttu-id="96b69-161">ID do benefício (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-161">Benefit ID (required)</span></span>
- <span data-ttu-id="96b69-162">Frequência</span><span class="sxs-lookup"><span data-stu-id="96b69-162">Frequency</span></span>
- <span data-ttu-id="96b69-163">Base</span><span class="sxs-lookup"><span data-stu-id="96b69-163">Basis</span></span>
- <span data-ttu-id="96b69-164">Valor ou taxa</span><span class="sxs-lookup"><span data-stu-id="96b69-164">Amount or rate</span></span>
- <span data-ttu-id="96b69-165">Código de ganhos</span><span class="sxs-lookup"><span data-stu-id="96b69-165">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="96b69-166">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="96b69-166">Supported frequencies</span></span> 

- <span data-ttu-id="96b69-167">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="96b69-167">Weekly</span></span>
- <span data-ttu-id="96b69-168">Por quinzena</span><span class="sxs-lookup"><span data-stu-id="96b69-168">Bi-weekly</span></span>
- <span data-ttu-id="96b69-169">Quinzenal</span><span class="sxs-lookup"><span data-stu-id="96b69-169">Semi-monthly</span></span>
- <span data-ttu-id="96b69-170">Mensalmente</span><span class="sxs-lookup"><span data-stu-id="96b69-170">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="96b69-171">Bases com suporte</span><span class="sxs-lookup"><span data-stu-id="96b69-171">Supported bases</span></span> 

- <span data-ttu-id="96b69-172">Valor fixo</span><span class="sxs-lookup"><span data-stu-id="96b69-172">Fixed amount</span></span>
- <span data-ttu-id="96b69-173">Percentual de ganhos</span><span class="sxs-lookup"><span data-stu-id="96b69-173">Percent of earnings</span></span>
- <span data-ttu-id="96b69-174">Horas produtivas</span><span class="sxs-lookup"><span data-stu-id="96b69-174">Productive hours</span></span>

<span data-ttu-id="96b69-175">O Dayforce cria as deduções a seguir, com base no impacto da folha de pagamento definido no plano de benefícios.</span><span class="sxs-lookup"><span data-stu-id="96b69-175">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="96b69-176">Seleção no Talent</span><span class="sxs-lookup"><span data-stu-id="96b69-176">Selection in Talent</span></span>        | <span data-ttu-id="96b69-177">Resultado no Dayforce</span><span class="sxs-lookup"><span data-stu-id="96b69-177">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="96b69-178">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="96b69-178">None</span></span>                       | <span data-ttu-id="96b69-179">Nenhuma dedução é criada.</span><span class="sxs-lookup"><span data-stu-id="96b69-179">No deduction is created.</span></span>                      |
| <span data-ttu-id="96b69-180">Somente dedução</span><span class="sxs-lookup"><span data-stu-id="96b69-180">Deduction only</span></span>             | <span data-ttu-id="96b69-181">Uma dedução de funcionário é criada.</span><span class="sxs-lookup"><span data-stu-id="96b69-181">An employee deduction is created.</span></span>             |
| <span data-ttu-id="96b69-182">Somente contribuição</span><span class="sxs-lookup"><span data-stu-id="96b69-182">Contribution only</span></span>          | <span data-ttu-id="96b69-183">Uma dedução de empregador é criada.</span><span class="sxs-lookup"><span data-stu-id="96b69-183">An employer deduction is created.</span></span>             |
| <span data-ttu-id="96b69-184">Dedução e contribuição</span><span class="sxs-lookup"><span data-stu-id="96b69-184">Deduction and contribution</span></span> | <span data-ttu-id="96b69-185">Deduções de funcionário e empregador são criadas.</span><span class="sxs-lookup"><span data-stu-id="96b69-185">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="96b69-186">Para obter mais informações sobre como definir e gerenciar um programa de benefícios, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="96b69-186">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="96b69-187">Entregar um programa de benefícios do funcionário</span><span class="sxs-lookup"><span data-stu-id="96b69-187">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="96b69-188">Criar um novo benefício</span><span class="sxs-lookup"><span data-stu-id="96b69-188">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="96b69-189">Definir regras e políticas de qualificação para o benefício</span><span class="sxs-lookup"><span data-stu-id="96b69-189">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="96b69-190">Inscrever e remover benefícios de trabalhadores</span><span class="sxs-lookup"><span data-stu-id="96b69-190">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="96b69-191">Remuneração</span><span class="sxs-lookup"><span data-stu-id="96b69-191">Compensation</span></span> 

<span data-ttu-id="96b69-192">O gerenciamento de remuneração é usado para controlar o pagamento do salário base e de prêmios.</span><span class="sxs-lookup"><span data-stu-id="96b69-192">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="96b69-193">Os aumentos no salário base fixo e nos prêmios de um funcionário são controlados por meio de planos de remuneração fixos.</span><span class="sxs-lookup"><span data-stu-id="96b69-193">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="96b69-194">O pagamento de incentivos, como pagamentos de bônus, prêmios por desempenho, opções de ação e concessões, além de prêmios únicos, são controlados por meio de planos de remuneração variável.</span><span class="sxs-lookup"><span data-stu-id="96b69-194">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="96b69-195">O Dayforce usa informações de remuneração para calcular a taxa por hora ou anual de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="96b69-195">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="96b69-196">Planos de remuneração fixa e conversões de taxa de pagamento são necessários.</span><span class="sxs-lookup"><span data-stu-id="96b69-196">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="96b69-197">Os funcionários devem estar associados a um plano de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="96b69-197">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="96b69-198">Para obter mais informações sobre planos de remuneração, veja os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="96b69-198">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="96b69-199">Criar planos de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="96b69-199">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="96b69-200">Criar planos de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="96b69-200">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="96b69-201">Desenvolver estrutura e planos de remuneração/salário</span><span class="sxs-lookup"><span data-stu-id="96b69-201">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="96b69-202">Processar remuneração</span><span class="sxs-lookup"><span data-stu-id="96b69-202">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="96b69-203">Definir processo de remuneração e calcular resultados</span><span class="sxs-lookup"><span data-stu-id="96b69-203">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="96b69-204">Inscrever um funcionário em um plano de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="96b69-204">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="96b69-205">Inscrever um funcionário em um plano de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="96b69-205">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="96b69-206">Trabalhos</span><span class="sxs-lookup"><span data-stu-id="96b69-206">Jobs</span></span> 

<span data-ttu-id="96b69-207">Um trabalho é um conjunto de tarefas e responsabilidades exigidas de uma pessoa que realiza um trabalho.</span><span class="sxs-lookup"><span data-stu-id="96b69-207">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="96b69-208">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="96b69-208">For more information, see the following topics:</span></span>

- [<span data-ttu-id="96b69-209">Configurando os componentes de um trabalho</span><span class="sxs-lookup"><span data-stu-id="96b69-209">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="96b69-210">Definir novos trabalhos</span><span class="sxs-lookup"><span data-stu-id="96b69-210">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="96b69-211">Posições</span><span class="sxs-lookup"><span data-stu-id="96b69-211">Positions</span></span>

<span data-ttu-id="96b69-212">Um cargo é uma instância individual de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="96b69-212">A position is an individual instance of a job.</span></span> <span data-ttu-id="96b69-213">Por exemplo, a posição "Gerente de vendas (Leste)" é uma das posições associadas ao trabalho "Gerente de vendas".</span><span class="sxs-lookup"><span data-stu-id="96b69-213">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="96b69-214">Uma posição existe em um departamento.</span><span class="sxs-lookup"><span data-stu-id="96b69-214">A position exists in a department.</span></span> <span data-ttu-id="96b69-215">Apenas um trabalhador pode ser associado a cada posição.</span><span class="sxs-lookup"><span data-stu-id="96b69-215">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="96b69-216">Considere os seguintes dados e configurações ao configurar as posições:</span><span class="sxs-lookup"><span data-stu-id="96b69-216">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="96b69-217">Posição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-217">Position (required)</span></span>
- <span data-ttu-id="96b69-218">Descrição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-218">Description (required)</span></span>
- <span data-ttu-id="96b69-219">Trabalho (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-219">Job (required)</span></span>
- <span data-ttu-id="96b69-220">Departamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-220">Department (required)</span></span>
- <span data-ttu-id="96b69-221">Tipo de posição (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-221">Position type (required)</span></span>
- <span data-ttu-id="96b69-222">Equivalente ao horário integral</span><span class="sxs-lookup"><span data-stu-id="96b69-222">Full-time equivalent</span></span>
- <span data-ttu-id="96b69-223">Horas normais anuais (obrigatórias)</span><span class="sxs-lookup"><span data-stu-id="96b69-223">Annual regular hours (required)</span></span>
- <span data-ttu-id="96b69-224">Pago por entidade legal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-224">Paid by legal entity (required)</span></span>
- <span data-ttu-id="96b69-225">Ciclo de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-225">Pay cycle (required)</span></span>
- <span data-ttu-id="96b69-226">Dimensão financeira padrão – Centro de custo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-226">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="96b69-227">Atribuição do trabalhador – Trabalhador, início da atribuição, fim da atribuição, código de motivo</span><span class="sxs-lookup"><span data-stu-id="96b69-227">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="96b69-228">Se várias posições no mesmo departamento estiverem associadas ao mesmo trabalho, elas serão consolidadas em uma única posição no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="96b69-228">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="96b69-229">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="96b69-229">For more information, see the following topics:</span></span>

- [<span data-ttu-id="96b69-230">Organizar sua força de trabalho usando departamentos, trabalhos e posições</span><span class="sxs-lookup"><span data-stu-id="96b69-230">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="96b69-231">Configurar posições</span><span class="sxs-lookup"><span data-stu-id="96b69-231">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="96b69-232">Departamentos</span><span class="sxs-lookup"><span data-stu-id="96b69-232">Departments</span></span>

<span data-ttu-id="96b69-233">Um departamento é uma unidade operacional que representa uma categoria ou uma área funcional de uma organização.</span><span class="sxs-lookup"><span data-stu-id="96b69-233">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="96b69-234">Um departamento é responsável por uma área específica da organização, como vendas, contabilidade ou recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="96b69-234">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="96b69-235">Você pode usar departamentos para relatar áreas funcionais.</span><span class="sxs-lookup"><span data-stu-id="96b69-235">You can use departments to report on functional areas.</span></span> <span data-ttu-id="96b69-236">Os departamentos podem ter a responsabilidade de lucros e perdas.</span><span class="sxs-lookup"><span data-stu-id="96b69-236">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="96b69-237">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="96b69-237">For more information, see the following topics:</span></span>

- [<span data-ttu-id="96b69-238">Criar um departamento e associá-lo à hierarquia de departamentos</span><span class="sxs-lookup"><span data-stu-id="96b69-238">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="96b69-239">Definir novos departamentos</span><span class="sxs-lookup"><span data-stu-id="96b69-239">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="96b69-240">Ciclos de pagamento e períodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="96b69-240">Pay cycles and pay periods</span></span>

<span data-ttu-id="96b69-241">Um ciclo de pagamento determina a frequência com que a folha de pagamento é executada e os dias específicos em que os trabalhadores são pagos.</span><span class="sxs-lookup"><span data-stu-id="96b69-241">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="96b69-242">Por exemplo, um ciclo de pagamento pode ser mensal e os funcionários podem ser pagos no último dia do mês.</span><span class="sxs-lookup"><span data-stu-id="96b69-242">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="96b69-243">Como alternativa, um ciclo de pagamento pode ser semanal e os funcionários podem ser pagos na terça-feira após o término do período de pagamento.</span><span class="sxs-lookup"><span data-stu-id="96b69-243">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="96b69-244">Ciclos de pagamento são atribuídos a posições para controlar quando os trabalhadores nessas posições são pagos.</span><span class="sxs-lookup"><span data-stu-id="96b69-244">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="96b69-245">Após a criação dos ciclos de pagamento, você pode gerar períodos de pagamento para cada ciclo.</span><span class="sxs-lookup"><span data-stu-id="96b69-245">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="96b69-246">Cada período de pagamento inclui uma data de pagamento padrão baseada nas informações que você fornece.</span><span class="sxs-lookup"><span data-stu-id="96b69-246">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="96b69-247">No entanto, você pode modificar a data de pagamento padrão em um período de pagamento para permitir exceções (por exemplo, quando a data de pagamento cai em um feriado).</span><span class="sxs-lookup"><span data-stu-id="96b69-247">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="96b69-248">As seguintes informações são usadas no Dayforce:</span><span class="sxs-lookup"><span data-stu-id="96b69-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="96b69-249">Ciclo de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-249">Pay cycle (required)</span></span>
- <span data-ttu-id="96b69-250">Frequência do ciclo de pagamento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-250">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="96b69-251">Data de início do período (primeiro período de pagamento obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-251">Period start date (first pay period required)</span></span>
- <span data-ttu-id="96b69-252">Data de pagamento padrão (primeiro período de pagamento obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-252">Default payment date (first pay period required)</span></span>

<span data-ttu-id="96b69-253">Essas informações são integradas ao Dayforce como grupos de pagamento e são separadas por país ou região para cada ciclo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="96b69-253">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="96b69-254">Pelo menos um período de pagamento deve ser gerado antes da integração.</span><span class="sxs-lookup"><span data-stu-id="96b69-254">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="96b69-255">O Dayforce gera datas de pagamento e calendários do grupo de pagamento, com base na data de início do primeiro período de pagamento e na data de pagamento padrão configurada no Talent.</span><span class="sxs-lookup"><span data-stu-id="96b69-255">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="96b69-256">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="96b69-256">Earning codes</span></span>

<span data-ttu-id="96b69-257">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="96b69-257">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="96b69-258">Os códigos têm vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="96b69-258">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="96b69-259">As seguintes informações são usadas no Dayforce:</span><span class="sxs-lookup"><span data-stu-id="96b69-259">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="96b69-260">Código de ganhos (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-260">Earning Code (required)</span></span>
- <span data-ttu-id="96b69-261">descrição</span><span class="sxs-lookup"><span data-stu-id="96b69-261">Description</span></span>
- <span data-ttu-id="96b69-262">Unidade de medida</span><span class="sxs-lookup"><span data-stu-id="96b69-262">Unit of measure</span></span>
- <span data-ttu-id="96b69-263">Produtivo</span><span class="sxs-lookup"><span data-stu-id="96b69-263">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="96b69-264">Dados do trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-264">Worker data</span></span>

<span data-ttu-id="96b69-265">Os registros dos vários tipos de trabalhadores que você tem são importantes para o RH e sistemas de folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="96b69-265">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="96b69-266">As informações inseridas podem ser usadas para rastrear trabalhadores e informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="96b69-266">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="96b69-267">Você pode manter estas informações para trabalhadores:</span><span class="sxs-lookup"><span data-stu-id="96b69-267">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="96b69-268">**Básicas** – mantenha informações básicas do trabalhador, como informações de contato, demográficas, de identificação, sobre a família, o status de serviço militar, informações de exilado, contatos pessoais e de emergência.</span><span class="sxs-lookup"><span data-stu-id="96b69-268">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="96b69-269">**Emprego** – mantenha informações sobre o emprego dos trabalhadores, como a afiliação da empresa ou organização, a atribuição de posição, as datas inicial e final, a qualificação para trabalho, o contrato de trabalho, a pensão, férias e as informações de mudança.</span><span class="sxs-lookup"><span data-stu-id="96b69-269">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="96b69-270">**Licença e ausência** – mantenha informações sobre as ausências dos trabalhadores, como o calendário de trabalho, as transações de ausência e a configuração de ausência.</span><span class="sxs-lookup"><span data-stu-id="96b69-270">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="96b69-271">**Remuneração e folha de pagamento** – mantenha informações sobre os planos de remuneração e as informações de folha de pagamento de trabalhadores, como o registro do plano, prêmios, o desempenho, a comissão, informações sobre impostos, aposentadoria e deduções do salário.</span><span class="sxs-lookup"><span data-stu-id="96b69-271">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="96b69-272">Ao inserir informações do trabalhador, tenha em mente os dados e configurações a seguir usados no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="96b69-272">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="96b69-273">Informações gerais</span><span class="sxs-lookup"><span data-stu-id="96b69-273">General information</span></span>

- <span data-ttu-id="96b69-274">Número de equipe (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-274">Personnel number (required)</span></span>
- <span data-ttu-id="96b69-275">Nome (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-275">First name (required)</span></span>
- <span data-ttu-id="96b69-276">Sobrenome (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-276">Last name (required)</span></span>
- <span data-ttu-id="96b69-277">Nome do meio</span><span class="sxs-lookup"><span data-stu-id="96b69-277">Middle name</span></span>
- <span data-ttu-id="96b69-278">Aniversário de tempo de serviço</span><span class="sxs-lookup"><span data-stu-id="96b69-278">Seniority date</span></span>
- <span data-ttu-id="96b69-279">Conhecido como</span><span class="sxs-lookup"><span data-stu-id="96b69-279">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="96b69-280">Informações pessoais</span><span class="sxs-lookup"><span data-stu-id="96b69-280">Personal information</span></span>

- <span data-ttu-id="96b69-281">Estado civil (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-281">Marital status (required)</span></span>
- <span data-ttu-id="96b69-282">Data de nascimento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-282">Birth date (required)</span></span>
- <span data-ttu-id="96b69-283">Sexo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-283">Gender (required)</span></span>
- <span data-ttu-id="96b69-284">Pessoa portadora de deficiências</span><span class="sxs-lookup"><span data-stu-id="96b69-284">Person with disabilities</span></span>
- <span data-ttu-id="96b69-285">Região do país de nacionalidade (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="96b69-285">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="96b69-286">Informações de endereço</span><span class="sxs-lookup"><span data-stu-id="96b69-286">Address information</span></span>

- <span data-ttu-id="96b69-287">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-287">Primary (required)</span></span>
- <span data-ttu-id="96b69-288">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-288">Country/region (required)</span></span>
- <span data-ttu-id="96b69-289">CEP (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-289">Postal code (required)</span></span>
- <span data-ttu-id="96b69-290">Número da rua (obrigatório) (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="96b69-290">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="96b69-291">Complemento do edifício (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="96b69-291">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="96b69-292">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-292">City (required)</span></span>
- <span data-ttu-id="96b69-293">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-293">State (required)</span></span>
- <span data-ttu-id="96b69-294">Município (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-294">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="96b69-295">Informações de contato</span><span class="sxs-lookup"><span data-stu-id="96b69-295">Contact information</span></span> 

- <span data-ttu-id="96b69-296">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-296">Primary (required)</span></span>
- <span data-ttu-id="96b69-297">Número de contato (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-297">Contact number (required)</span></span>
- <span data-ttu-id="96b69-298">Extensão</span><span class="sxs-lookup"><span data-stu-id="96b69-298">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="96b69-299">Informações sobre folha de pagamento e códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="96b69-299">Payroll information and earning codes</span></span>

<span data-ttu-id="96b69-300">Os funcionários podem receber ganhos específicos com uma determinada frequência de pagamento e ter um método de pagamento preferencial.</span><span class="sxs-lookup"><span data-stu-id="96b69-300">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="96b69-301">Os campos a seguir são usados no Dayforce para ajudar a garantir que essas preferências e configurações sejam usadas.</span><span class="sxs-lookup"><span data-stu-id="96b69-301">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="96b69-302">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="96b69-302">Earning codes</span></span>

- <span data-ttu-id="96b69-303">Posição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-303">Position (required)</span></span>
- <span data-ttu-id="96b69-304">Código de ganhos (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-304">Earning Code (required)</span></span>
- <span data-ttu-id="96b69-305">Frequência (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-305">Frequency (required)</span></span>
- <span data-ttu-id="96b69-306">Valor (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-306">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="96b69-307">Informações da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="96b69-307">Payroll information</span></span>

- <span data-ttu-id="96b69-308">Método de Pagamento</span><span class="sxs-lookup"><span data-stu-id="96b69-308">Payment Method</span></span>
- <span data-ttu-id="96b69-309">Região econômica (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-309">Economic Region (required)</span></span>
- <span data-ttu-id="96b69-310">ID de Benefícios do Funcionário</span><span class="sxs-lookup"><span data-stu-id="96b69-310">Employee Benefits ID</span></span>
- <span data-ttu-id="96b69-311">Número de ID nacional (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-311">National ID Number (required)</span></span>
- <span data-ttu-id="96b69-312">Número de serviço militar</span><span class="sxs-lookup"><span data-stu-id="96b69-312">Military Service Number</span></span>
- <span data-ttu-id="96b69-313">ID de turno (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-313">Shift ID (required)</span></span>
- <span data-ttu-id="96b69-314">Número fiscal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-314">Tax Number (required)</span></span>
- <span data-ttu-id="96b69-315">ID do sindicato (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-315">Union ID (required)</span></span>
- <span data-ttu-id="96b69-316">ID do dia útil (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-316">Work Day ID (required)</span></span>
- <span data-ttu-id="96b69-317">Número de autorização de trabalho</span><span class="sxs-lookup"><span data-stu-id="96b69-317">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="96b69-318">Para o método de pagamento, o México permite **Pagamento à vista**, **Cheque** (o cheque físico da empresa) e **Pagamento Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="96b69-318">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="96b69-319">Se nenhum método de pagamento for especificado, **Cheque** é usado por padrão.</span><span class="sxs-lookup"><span data-stu-id="96b69-319">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="96b69-320">Detalhes do emprego</span><span class="sxs-lookup"><span data-stu-id="96b69-320">Employment details</span></span>

<span data-ttu-id="96b69-321">O histórico de detalhes de emprego é usado como principal informação para derivar os status de contratação, rescisão e recontratação de um funcionário no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="96b69-321">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="96b69-322">O Dayforce suporta apenas um registro de emprego ativo de cada vez.</span><span class="sxs-lookup"><span data-stu-id="96b69-322">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="96b69-323">Data de início do emprego (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-323">Employment start date (required)</span></span>
- <span data-ttu-id="96b69-324">Data final do emprego</span><span class="sxs-lookup"><span data-stu-id="96b69-324">Employment end date</span></span>
- <span data-ttu-id="96b69-325">Data de início</span><span class="sxs-lookup"><span data-stu-id="96b69-325">Start date</span></span>
- <span data-ttu-id="96b69-326">Data inicial ajustada</span><span class="sxs-lookup"><span data-stu-id="96b69-326">Adjusted start date</span></span>
- <span data-ttu-id="96b69-327">Data de rescisão (obrigatória após a rescisão)</span><span class="sxs-lookup"><span data-stu-id="96b69-327">Termination date (required upon termination)</span></span>
- <span data-ttu-id="96b69-328">Motivo da rescisão (obrigatória após a rescisão)</span><span class="sxs-lookup"><span data-stu-id="96b69-328">Termination reason (required upon termination)</span></span>

<span data-ttu-id="96b69-329">As principais datas de um funcionário são derivadas usando-se as informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="96b69-329">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="96b69-330">Talent</span><span class="sxs-lookup"><span data-stu-id="96b69-330">Talent</span></span>                | <span data-ttu-id="96b69-331">Dayforce</span><span class="sxs-lookup"><span data-stu-id="96b69-331">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="96b69-332">Data de contratação mais recente</span><span class="sxs-lookup"><span data-stu-id="96b69-332">Most recent hire date</span></span> | <span data-ttu-id="96b69-333">Início de emprego do registro histórico de emprego atual não terminado</span><span class="sxs-lookup"><span data-stu-id="96b69-333">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="96b69-334">Data da rescisão</span><span class="sxs-lookup"><span data-stu-id="96b69-334">Termination date</span></span>      | <span data-ttu-id="96b69-335">Data de rescisão do registro histórico de emprego atual não terminado</span><span class="sxs-lookup"><span data-stu-id="96b69-335">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="96b69-336">Data de início</span><span class="sxs-lookup"><span data-stu-id="96b69-336">Start date</span></span>            | <span data-ttu-id="96b69-337">Data de início ajustada, data de início ou início de emprego do registro histórico de emprego não ativo atual</span><span class="sxs-lookup"><span data-stu-id="96b69-337">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="96b69-338">Data original de contratação</span><span class="sxs-lookup"><span data-stu-id="96b69-338">Original hire date</span></span>    | <span data-ttu-id="96b69-339">Início de emprego do registro histórico de emprego mais antigo</span><span class="sxs-lookup"><span data-stu-id="96b69-339">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="96b69-340">Remuneração</span><span class="sxs-lookup"><span data-stu-id="96b69-340">Compensation</span></span>

<span data-ttu-id="96b69-341">Um plano de remuneração fixa deve estar associado à posição principal de cada funcionário durante um período de emprego.</span><span class="sxs-lookup"><span data-stu-id="96b69-341">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="96b69-342">Esse período tem início na data em que o funcionário foi contratado (ou na data de início do emprego) e continua até a rescisão.</span><span class="sxs-lookup"><span data-stu-id="96b69-342">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="96b69-343">Data de vigência (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-343">Effective Date (required)</span></span>
- <span data-ttu-id="96b69-344">Data de validade</span><span class="sxs-lookup"><span data-stu-id="96b69-344">Expiration date</span></span>
- <span data-ttu-id="96b69-345">Taxa de pagamento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-345">Pay Rate (required)</span></span>
- <span data-ttu-id="96b69-346">Conversões de taxa de pagamento (obrigatórias)</span><span class="sxs-lookup"><span data-stu-id="96b69-346">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="96b69-347">Equivalente anual (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-347">Annual equivalent (required)</span></span>
- <span data-ttu-id="96b69-348">Equivalente por hora (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-348">Hourly equivalent (required)</span></span>

<span data-ttu-id="96b69-349">Se um funcionário por hora tiver várias posições, a remuneração fixa da posição principal é importada para o Dayforce como a taxa base/salário do nível do funcionário.</span><span class="sxs-lookup"><span data-stu-id="96b69-349">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="96b69-350">Para posições não principais, a taxa por hora é salva na posição correspondente no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="96b69-350">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="96b69-351">Se um funcionário assalariado tiver várias posições, a taxa acumulada de horas e o salário anual em todas as posições ativas serão derivados e usados como a taxa base/salário do nível do funcionário.</span><span class="sxs-lookup"><span data-stu-id="96b69-351">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="96b69-352">Números de identificação</span><span class="sxs-lookup"><span data-stu-id="96b69-352">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="96b69-353">Cadastro de Pessoa Física (CPF)</span><span class="sxs-lookup"><span data-stu-id="96b69-353">Social Security identifier</span></span> 

<span data-ttu-id="96b69-354">Todos os funcionários devem ter um identificador principal.</span><span class="sxs-lookup"><span data-stu-id="96b69-354">Every employee must have one primary identifier.</span></span> <span data-ttu-id="96b69-355">Esse identificador deve ser o tipo de identificação **CPF**.</span><span class="sxs-lookup"><span data-stu-id="96b69-355">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="96b69-356">No Dayforce, ele é derivado automaticamente como o identificador de pessoa física do funcionário necessário para a contratação.</span><span class="sxs-lookup"><span data-stu-id="96b69-356">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="96b69-357">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-357">Primary (required)</span></span>
- <span data-ttu-id="96b69-358">Tipo de identificação = "CPF"</span><span class="sxs-lookup"><span data-stu-id="96b69-358">Identification Type = "SSN"</span></span>
- <span data-ttu-id="96b69-359">Data da emissão</span><span class="sxs-lookup"><span data-stu-id="96b69-359">Issued Date</span></span>
- <span data-ttu-id="96b69-360">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="96b69-360">Expiration Date</span></span>

<span data-ttu-id="96b69-361">Os funcionários podem declarar vários números de identificação do tipo de identificação **CPF**.</span><span class="sxs-lookup"><span data-stu-id="96b69-361">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="96b69-362">No entanto, somente o registro marcado como **Principal** será integrado ao Dayforce, independentemente de o número estar ativo ou expirado.</span><span class="sxs-lookup"><span data-stu-id="96b69-362">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="96b69-363">Contas bancárias e pagamentos</span><span class="sxs-lookup"><span data-stu-id="96b69-363">Bank accounts and disbursements</span></span>

<span data-ttu-id="96b69-364">Informações de conta bancária válidas devem ser inseridas para qualquer funcionário que opte por ser pago por meio de transferências bancárias.</span><span class="sxs-lookup"><span data-stu-id="96b69-364">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="96b69-365">Talent</span><span class="sxs-lookup"><span data-stu-id="96b69-365">Talent</span></span>                         | <span data-ttu-id="96b69-366">Dayforce</span><span class="sxs-lookup"><span data-stu-id="96b69-366">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="96b69-367">Número da conta bancária (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-367">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="96b69-368">Código SWIFT (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-368">SWIFT code (required)</span></span>          | <span data-ttu-id="96b69-369">Campo **ID do banco** usado no processamento da folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="96b69-369">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="96b69-370">Número da agência (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-370">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="96b69-371">Tipo de conta bancária (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-371">Bank account type (required)</span></span>   | <span data-ttu-id="96b69-372">Campo **Tipo de conta** usado no processamento da folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="96b69-372">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="96b69-373">Os valores com suporte incluem **Movimento** e **Folha de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="96b69-373">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="96b69-374">Os funcionários que optarem por serem pagos por meio de transferências bancárias deverão fornecer um link para uma conta de pendência em uma entidade legal que tenha seu endereço principal no México e esteja associada a uma conta bancária válida de um banco mexicano.</span><span class="sxs-lookup"><span data-stu-id="96b69-374">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="96b69-375">Todas as outras contas que não são de pendência são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="96b69-375">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="96b69-376">Informações de endereço</span><span class="sxs-lookup"><span data-stu-id="96b69-376">Address information</span></span>

<span data-ttu-id="96b69-377">Todos os funcionários devem ter um local principal.</span><span class="sxs-lookup"><span data-stu-id="96b69-377">Every employee must have one primary location.</span></span> <span data-ttu-id="96b69-378">No Dayforce, esse local é usado para determinar a residência principal do funcionário para fins fiscais.</span><span class="sxs-lookup"><span data-stu-id="96b69-378">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="96b69-379">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-379">Primary (required)</span></span>
- <span data-ttu-id="96b69-380">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-380">Country/region (required)</span></span>
- <span data-ttu-id="96b69-381">CEP (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-381">Zip/postal code (required)</span></span>
- <span data-ttu-id="96b69-382">Rua (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-382">Street (required)</span></span>
- <span data-ttu-id="96b69-383">Número da rua (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-383">Street Number (required)</span></span>
- <span data-ttu-id="96b69-384">Complemento do edifício</span><span class="sxs-lookup"><span data-stu-id="96b69-384">Building Complement</span></span>
- <span data-ttu-id="96b69-385">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-385">City (required)</span></span>
- <span data-ttu-id="96b69-386">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-386">State (required)</span></span>
- <span data-ttu-id="96b69-387">Município (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-387">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="96b69-388">Configurar seus dados para gerar folha de pagamento nos Estados Unidos e no Canadá</span><span class="sxs-lookup"><span data-stu-id="96b69-388">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="96b69-389">Se você está gerando pagamento para funcionários nos Estados Unidos e no Canadá, os seguintes elementos devem ser configurados:</span><span class="sxs-lookup"><span data-stu-id="96b69-389">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="96b69-390">Departamentos são necessários em posições.</span><span class="sxs-lookup"><span data-stu-id="96b69-390">Departments are required on positions.</span></span>
- <span data-ttu-id="96b69-391">Os centros de custo devem ser definidos como dimensões financeiras e ser o primeiro elemento na sequência de dimensão financeira padrão.</span><span class="sxs-lookup"><span data-stu-id="96b69-391">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="96b69-392">Você pode configurar o Talent para exigir que Posições especifique um Departamento.</span><span class="sxs-lookup"><span data-stu-id="96b69-392">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="96b69-393">Para isso, acesse **Posições Compartilhadas de Recursos Humanos > Posições > Exigir departamentos nas posições**.</span><span class="sxs-lookup"><span data-stu-id="96b69-393">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="96b69-394">Recomendamos que esta configuração seja imposta para a integração.</span><span class="sxs-lookup"><span data-stu-id="96b69-394">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="96b69-395">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="96b69-395">Job types</span></span>

<span data-ttu-id="96b69-396">Os tipos de trabalho são usados para agrupar trabalhos semelhantes em categorias.</span><span class="sxs-lookup"><span data-stu-id="96b69-396">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="96b69-397">Os tipos de trabalho são necessários para processar a folha de pagamento nos Estados Unidos e no Canadá.</span><span class="sxs-lookup"><span data-stu-id="96b69-397">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="96b69-398">Os exemplos de tipos de trabalho incluem horário integral e meio período ou salário e pagamento por hora.</span><span class="sxs-lookup"><span data-stu-id="96b69-398">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="96b69-399">Os tipos de trabalho são mapeados para o Dayforce como tipos de pagamento que indicam se um funcionário é pago por hora ou assalariado.</span><span class="sxs-lookup"><span data-stu-id="96b69-399">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="96b69-400">Os seguintes tipos de trabalho e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="96b69-400">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="96b69-401">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="96b69-401">Job type</span></span>   | <span data-ttu-id="96b69-402">descrição</span><span class="sxs-lookup"><span data-stu-id="96b69-402">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="96b69-403">Por hora</span><span class="sxs-lookup"><span data-stu-id="96b69-403">Hourly</span></span>     | <span data-ttu-id="96b69-404">Por hora</span><span class="sxs-lookup"><span data-stu-id="96b69-404">Hourly</span></span>      |
| <span data-ttu-id="96b69-405">Assalariado</span><span class="sxs-lookup"><span data-stu-id="96b69-405">Salaried</span></span>   | <span data-ttu-id="96b69-406">Assalariado</span><span class="sxs-lookup"><span data-stu-id="96b69-406">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="96b69-407">Tipos de posição</span><span class="sxs-lookup"><span data-stu-id="96b69-407">Position types</span></span> 

<span data-ttu-id="96b69-408">Você usa os tipos de posição para descrever se a posição é de tempo integral, meio período ou de outra natureza.</span><span class="sxs-lookup"><span data-stu-id="96b69-408">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="96b69-409">Os tipos de posição são mapeados para o Dayforce como classes de pagamento que indicam se um funcionário é de tempo integral ou meio período.</span><span class="sxs-lookup"><span data-stu-id="96b69-409">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="96b69-410">Os seguintes tipos de posição e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="96b69-410">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="96b69-411">Tipo de posição</span><span class="sxs-lookup"><span data-stu-id="96b69-411">Position type</span></span>   | <span data-ttu-id="96b69-412">descrição</span><span class="sxs-lookup"><span data-stu-id="96b69-412">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="96b69-413">Horário integral</span><span class="sxs-lookup"><span data-stu-id="96b69-413">Full-time</span></span>       | <span data-ttu-id="96b69-414">Funcionário de tempo integral</span><span class="sxs-lookup"><span data-stu-id="96b69-414">Full time employee</span></span> |
| <span data-ttu-id="96b69-415">Meio período</span><span class="sxs-lookup"><span data-stu-id="96b69-415">Part-time</span></span>       | <span data-ttu-id="96b69-416">Funcionário de meio período</span><span class="sxs-lookup"><span data-stu-id="96b69-416">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="96b69-417">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="96b69-417">Reason codes</span></span>

<span data-ttu-id="96b69-418">Códigos de motivo fornecem informações sobre o status de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="96b69-418">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="96b69-419">Os códigos de motivo são mapeados para o Dayforce como motivos de status que indicam o motivo das alterações na posição de um funcionário ou no status de um emprego.</span><span class="sxs-lookup"><span data-stu-id="96b69-419">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="96b69-420">Os seguintes códigos de motivo e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="96b69-420">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="96b69-421">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="96b69-421">Reason code</span></span>    | <span data-ttu-id="96b69-422">descrição</span><span class="sxs-lookup"><span data-stu-id="96b69-422">Description</span></span>      | <span data-ttu-id="96b69-423">Cenários aplicáveis</span><span class="sxs-lookup"><span data-stu-id="96b69-423">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="96b69-424">DEMISSÃO</span><span class="sxs-lookup"><span data-stu-id="96b69-424">RESIGNATION</span></span>    | <span data-ttu-id="96b69-425">Demissão</span><span class="sxs-lookup"><span data-stu-id="96b69-425">Resignation</span></span>      | <span data-ttu-id="96b69-426">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-426">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-427">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="96b69-427">TERMINATION</span></span>    | <span data-ttu-id="96b69-428">Finalização</span><span class="sxs-lookup"><span data-stu-id="96b69-428">Termination</span></span>      | <span data-ttu-id="96b69-429">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-429">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-430">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="96b69-430">RETIREMENT</span></span>     | <span data-ttu-id="96b69-431">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="96b69-431">Retirement</span></span>       | <span data-ttu-id="96b69-432">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-432">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-433">OTHER</span><span class="sxs-lookup"><span data-stu-id="96b69-433">OTHER</span></span>          | <span data-ttu-id="96b69-434">Outros motivos</span><span class="sxs-lookup"><span data-stu-id="96b69-434">Other Reasons</span></span>    | <span data-ttu-id="96b69-435">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-435">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-436">DEATH</span><span class="sxs-lookup"><span data-stu-id="96b69-436">DEATH</span></span>          | <span data-ttu-id="96b69-437">Morte</span><span class="sxs-lookup"><span data-stu-id="96b69-437">Death</span></span>            | <span data-ttu-id="96b69-438">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-438">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-439">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="96b69-439">LEAVEOFABSENCE</span></span> | <span data-ttu-id="96b69-440">Licença</span><span class="sxs-lookup"><span data-stu-id="96b69-440">Leave of Absence</span></span> | <span data-ttu-id="96b69-441">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-441">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-442">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="96b69-442">CONTRACTEND</span></span>    | <span data-ttu-id="96b69-443">Fim do contrato</span><span class="sxs-lookup"><span data-stu-id="96b69-443">End of Contract</span></span>  | <span data-ttu-id="96b69-444">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-444">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-445">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="96b69-445">SALARYCHANGE</span></span>   | <span data-ttu-id="96b69-446">Alteração de salário</span><span class="sxs-lookup"><span data-stu-id="96b69-446">Change of Salary</span></span> | <span data-ttu-id="96b69-447">Remuneração</span><span class="sxs-lookup"><span data-stu-id="96b69-447">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="96b69-448">Estado civil</span><span class="sxs-lookup"><span data-stu-id="96b69-448">Marital status</span></span>

<span data-ttu-id="96b69-449">Os valores do estado civil são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="96b69-449">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="96b69-450">A tabela a seguir mostra como os valores do estado civil são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="96b69-450">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="96b69-451">Talent</span><span class="sxs-lookup"><span data-stu-id="96b69-451">Talent</span></span>                 | <span data-ttu-id="96b69-452">Dayforce</span><span class="sxs-lookup"><span data-stu-id="96b69-452">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="96b69-453">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="96b69-453">Married</span></span>                | <span data-ttu-id="96b69-454">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="96b69-454">Married</span></span>              |
| <span data-ttu-id="96b69-455">Única</span><span class="sxs-lookup"><span data-stu-id="96b69-455">Single</span></span>                 | <span data-ttu-id="96b69-456">Única</span><span class="sxs-lookup"><span data-stu-id="96b69-456">Single</span></span>               |
| <span data-ttu-id="96b69-457">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="96b69-457">Widowed</span></span>                | <span data-ttu-id="96b69-458">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="96b69-458">Widowed</span></span>              |
| <span data-ttu-id="96b69-459">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="96b69-459">Divorced</span></span>               | <span data-ttu-id="96b69-460">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="96b69-460">Divorced</span></span>             |
| <span data-ttu-id="96b69-461">Parceria Registrada</span><span class="sxs-lookup"><span data-stu-id="96b69-461">Registered Partnership</span></span> | <span data-ttu-id="96b69-462">Parceiro doméstico</span><span class="sxs-lookup"><span data-stu-id="96b69-462">Domestic Partnership</span></span> |
| <span data-ttu-id="96b69-463">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="96b69-463">None</span></span>                   | <span data-ttu-id="96b69-464">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="96b69-464">None</span></span>                 |
| <span data-ttu-id="96b69-465">Coabitando</span><span class="sxs-lookup"><span data-stu-id="96b69-465">Cohabiting</span></span>             | <span data-ttu-id="96b69-466">Coabitando</span><span class="sxs-lookup"><span data-stu-id="96b69-466">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="96b69-467">Sexo</span><span class="sxs-lookup"><span data-stu-id="96b69-467">Gender</span></span>

<span data-ttu-id="96b69-468">As designações de gênero são mapeadas para o Dayforce e convertidas, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="96b69-468">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="96b69-469">A tabela a seguir mostra como as designações de gênero são mapeadas para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="96b69-469">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="96b69-470">Talent</span><span class="sxs-lookup"><span data-stu-id="96b69-470">Talent</span></span>       | <span data-ttu-id="96b69-471">Dayforce</span><span class="sxs-lookup"><span data-stu-id="96b69-471">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="96b69-472">Masculino</span><span class="sxs-lookup"><span data-stu-id="96b69-472">Male</span></span>         | <span data-ttu-id="96b69-473">Masculino</span><span class="sxs-lookup"><span data-stu-id="96b69-473">Male</span></span>            |
| <span data-ttu-id="96b69-474">Feminino</span><span class="sxs-lookup"><span data-stu-id="96b69-474">Female</span></span>       | <span data-ttu-id="96b69-475">Feminino</span><span class="sxs-lookup"><span data-stu-id="96b69-475">Female</span></span>          |
| <span data-ttu-id="96b69-476">Não específico</span><span class="sxs-lookup"><span data-stu-id="96b69-476">Non-specific</span></span> | <span data-ttu-id="96b69-477">*Sem suporte*</span><span class="sxs-lookup"><span data-stu-id="96b69-477">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="96b69-478">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="96b69-478">Earning codes</span></span>

<span data-ttu-id="96b69-479">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="96b69-479">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="96b69-480">Os códigos abordam vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="96b69-480">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="96b69-481">Se uma frequência sem suporte for usada, a frequência **Cada pagamento** é usada por padrão para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="96b69-481">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="96b69-482">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="96b69-482">Supported frequencies</span></span>

- <span data-ttu-id="96b69-483">Todas</span><span class="sxs-lookup"><span data-stu-id="96b69-483">All</span></span>
- <span data-ttu-id="96b69-484">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="96b69-484">EVERYPAY</span></span>
- <span data-ttu-id="96b69-485">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="96b69-485">EACHPAYPERIOD</span></span>
- <span data-ttu-id="96b69-486">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="96b69-486">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="96b69-487">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="96b69-487">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="96b69-488">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-488">1OFMTH</span></span>
- <span data-ttu-id="96b69-489">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-489">LASTOFMTH</span></span>
- <span data-ttu-id="96b69-490">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-490">2OFMTH</span></span>
- <span data-ttu-id="96b69-491">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-491">3OFMTH</span></span>
- <span data-ttu-id="96b69-492">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-492">4OFMTH</span></span>
- <span data-ttu-id="96b69-493">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-493">5OFMTH</span></span>
- <span data-ttu-id="96b69-494">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-494">1N2OFMTH</span></span>
- <span data-ttu-id="96b69-495">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-495">3N4OFMTH</span></span>
- <span data-ttu-id="96b69-496">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-496">1N3OFMTH</span></span>
- <span data-ttu-id="96b69-497">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-497">1N4OFMTH</span></span>
- <span data-ttu-id="96b69-498">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-498">2N3OFMTH</span></span>
- <span data-ttu-id="96b69-499">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-499">2N4OFMTH</span></span>
- <span data-ttu-id="96b69-500">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-500">1N2N3OFMTH</span></span>
- <span data-ttu-id="96b69-501">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-501">1N2N4OFMTH</span></span>
- <span data-ttu-id="96b69-502">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-502">1N3N4OFMTH</span></span>
- <span data-ttu-id="96b69-503">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-503">2N3N4OFMTH</span></span>
- <span data-ttu-id="96b69-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="96b69-505">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="96b69-505">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="96b69-506">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="96b69-506">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="96b69-507">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="96b69-507">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="96b69-508">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="96b69-508">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="96b69-509">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="96b69-509">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="96b69-510">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="96b69-510">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="96b69-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="96b69-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="96b69-512">Endereços</span><span class="sxs-lookup"><span data-stu-id="96b69-512">Addresses</span></span>

<span data-ttu-id="96b69-513">A identificação de códigos específicos de país ou região, estado e município (municipalidade) exige formatos específicos que o Dayforce e os provedores no país/na região possam reconhecer.</span><span class="sxs-lookup"><span data-stu-id="96b69-513">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="96b69-514">Embora o formato das cidades seja flexível, todas as cidades devem estar associadas a um estado.</span><span class="sxs-lookup"><span data-stu-id="96b69-514">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="96b69-515">Talent</span><span class="sxs-lookup"><span data-stu-id="96b69-515">Talent</span></span>          | <span data-ttu-id="96b69-516">Dayforce</span><span class="sxs-lookup"><span data-stu-id="96b69-516">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="96b69-517">País/Região</span><span class="sxs-lookup"><span data-stu-id="96b69-517">Country/Region</span></span>  | <span data-ttu-id="96b69-518">Código do País</span><span class="sxs-lookup"><span data-stu-id="96b69-518">Country Code</span></span>          |
| <span data-ttu-id="96b69-519">CEP</span><span class="sxs-lookup"><span data-stu-id="96b69-519">Zip/Postal Code</span></span> | <span data-ttu-id="96b69-520">CEP</span><span class="sxs-lookup"><span data-stu-id="96b69-520">Postal Code</span></span>           |
| <span data-ttu-id="96b69-521">Estadual</span><span class="sxs-lookup"><span data-stu-id="96b69-521">State</span></span>           | <span data-ttu-id="96b69-522">Código de estado</span><span class="sxs-lookup"><span data-stu-id="96b69-522">State Code</span></span>            |
| <span data-ttu-id="96b69-523">Cidade</span><span class="sxs-lookup"><span data-stu-id="96b69-523">City</span></span>            | <span data-ttu-id="96b69-524">Cidade</span><span class="sxs-lookup"><span data-stu-id="96b69-524">City</span></span>                  |
| <span data-ttu-id="96b69-525">Região</span><span class="sxs-lookup"><span data-stu-id="96b69-525">County</span></span>          | <span data-ttu-id="96b69-526">Município (municipalidade)</span><span class="sxs-lookup"><span data-stu-id="96b69-526">County (Municipality)</span></span> |
| <span data-ttu-id="96b69-527">Rua</span><span class="sxs-lookup"><span data-stu-id="96b69-527">Street</span></span>          | <span data-ttu-id="96b69-528">Linha de endereço 1</span><span class="sxs-lookup"><span data-stu-id="96b69-528">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="96b69-529">Regiões fiscais</span><span class="sxs-lookup"><span data-stu-id="96b69-529">Tax regions</span></span>

<span data-ttu-id="96b69-530">Regiões fiscais são usadas para determinar os impostos apropriados a serem aplicados durante a geração da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="96b69-530">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="96b69-531">As regiões fiscais são mapeadas para o Dayforce como endereços de localização.</span><span class="sxs-lookup"><span data-stu-id="96b69-531">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="96b69-532">A região fiscal padrão deve estar associada à posição ativa do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="96b69-532">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="96b69-533">Região fiscal (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-533">Tax region (required)</span></span>
- <span data-ttu-id="96b69-534">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-534">Country/Region (required)</span></span>
- <span data-ttu-id="96b69-535">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="96b69-535">State (required)</span></span>
- <span data-ttu-id="96b69-536">Região</span><span class="sxs-lookup"><span data-stu-id="96b69-536">County</span></span> 
- <span data-ttu-id="96b69-537">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="96b69-537">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="96b69-538">Configurar seus dados para gerar folha de pagamento no México</span><span class="sxs-lookup"><span data-stu-id="96b69-538">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="96b69-539">Se você está gerando pagamento para funcionários no México, os seguintes elementos devem ser configurados:</span><span class="sxs-lookup"><span data-stu-id="96b69-539">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="96b69-540">Departamentos são necessários em posições.</span><span class="sxs-lookup"><span data-stu-id="96b69-540">Departments are required on positions.</span></span>
- <span data-ttu-id="96b69-541">Os centros de custo devem ser definidos como dimensões financeiras e ser o primeiro elemento na sequência de dimensão financeira padrão.</span><span class="sxs-lookup"><span data-stu-id="96b69-541">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="96b69-542">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="96b69-542">Job types</span></span>

<span data-ttu-id="96b69-543">Os tipos de trabalho são usados para agrupar trabalhos semelhantes em categorias.</span><span class="sxs-lookup"><span data-stu-id="96b69-543">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="96b69-544">Tipos de trabalho são necessários para processar a folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="96b69-544">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="96b69-545">Os exemplos de tipos de trabalho incluem horário integral e meio período ou salário e pagamento por hora.</span><span class="sxs-lookup"><span data-stu-id="96b69-545">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="96b69-546">Os tipos de trabalho são mapeados para o Dayforce como tipos de pagamento que indicam se um funcionário é pago por hora ou assalariado.</span><span class="sxs-lookup"><span data-stu-id="96b69-546">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="96b69-547">Os seguintes tipos de trabalho e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="96b69-547">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="96b69-548">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="96b69-548">Job type</span></span>   | <span data-ttu-id="96b69-549">descrição</span><span class="sxs-lookup"><span data-stu-id="96b69-549">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="96b69-550">Por hora</span><span class="sxs-lookup"><span data-stu-id="96b69-550">Hourly</span></span>     | <span data-ttu-id="96b69-551">MX por hora</span><span class="sxs-lookup"><span data-stu-id="96b69-551">MX Hourly</span></span>   |
| <span data-ttu-id="96b69-552">Assalariado</span><span class="sxs-lookup"><span data-stu-id="96b69-552">Salaried</span></span>   | <span data-ttu-id="96b69-553">MX assalariado</span><span class="sxs-lookup"><span data-stu-id="96b69-553">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="96b69-554">Tipos de posição</span><span class="sxs-lookup"><span data-stu-id="96b69-554">Position types</span></span> 

<span data-ttu-id="96b69-555">Você usa os tipos de posição para descrever se a posição é de tempo integral, meio período ou de outra natureza.</span><span class="sxs-lookup"><span data-stu-id="96b69-555">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="96b69-556">Os tipos de posição são mapeados para o Dayforce como classes de pagamento que indicam se um funcionário é de tempo integral ou meio período.</span><span class="sxs-lookup"><span data-stu-id="96b69-556">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="96b69-557">Os seguintes tipos de posição e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="96b69-557">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="96b69-558">Tipo de posição</span><span class="sxs-lookup"><span data-stu-id="96b69-558">Position type</span></span>   | <span data-ttu-id="96b69-559">descrição</span><span class="sxs-lookup"><span data-stu-id="96b69-559">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="96b69-560">Horário integral</span><span class="sxs-lookup"><span data-stu-id="96b69-560">Full-time</span></span>       | <span data-ttu-id="96b69-561">Funcionário de tempo integral</span><span class="sxs-lookup"><span data-stu-id="96b69-561">Full time employee</span></span> |
| <span data-ttu-id="96b69-562">Meio período</span><span class="sxs-lookup"><span data-stu-id="96b69-562">Part-time</span></span>       | <span data-ttu-id="96b69-563">Funcionário de meio período</span><span class="sxs-lookup"><span data-stu-id="96b69-563">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="96b69-564">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="96b69-564">Reason codes</span></span>

<span data-ttu-id="96b69-565">Códigos de motivo fornecem informações sobre o status de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="96b69-565">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="96b69-566">Os códigos de motivo são mapeados para o Dayforce como motivos de status que indicam o motivo das alterações na posição de um funcionário ou no status de um emprego.</span><span class="sxs-lookup"><span data-stu-id="96b69-566">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="96b69-567">Os seguintes códigos de motivo e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="96b69-567">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="96b69-568">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="96b69-568">Reason code</span></span>            | <span data-ttu-id="96b69-569">descrição</span><span class="sxs-lookup"><span data-stu-id="96b69-569">Description</span></span>                    | <span data-ttu-id="96b69-570">Cenários aplicáveis</span><span class="sxs-lookup"><span data-stu-id="96b69-570">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="96b69-571">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="96b69-571">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="96b69-572">Partida antes da primeira folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="96b69-572">Departure before first payroll</span></span> | <span data-ttu-id="96b69-573">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-573">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-574">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="96b69-574">RESIGNATION</span></span>            | <span data-ttu-id="96b69-575">Demissão</span><span class="sxs-lookup"><span data-stu-id="96b69-575">Resignation</span></span>                    | <span data-ttu-id="96b69-576">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-576">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-577">PENSION</span><span class="sxs-lookup"><span data-stu-id="96b69-577">PENSION</span></span>                | <span data-ttu-id="96b69-578">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="96b69-578">Pension</span></span>                        | <span data-ttu-id="96b69-579">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-579">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-580">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="96b69-580">TERMINATION</span></span>            | <span data-ttu-id="96b69-581">Finalização</span><span class="sxs-lookup"><span data-stu-id="96b69-581">Termination</span></span>                    | <span data-ttu-id="96b69-582">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-582">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-583">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="96b69-583">RETIREMENT</span></span>             | <span data-ttu-id="96b69-584">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="96b69-584">Retirement</span></span>                     | <span data-ttu-id="96b69-585">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-585">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-586">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="96b69-586">ABSENTEE</span></span>               | <span data-ttu-id="96b69-587">Absentista</span><span class="sxs-lookup"><span data-stu-id="96b69-587">Absentee</span></span>                       | <span data-ttu-id="96b69-588">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-588">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-589">OTHER</span><span class="sxs-lookup"><span data-stu-id="96b69-589">OTHER</span></span>                  | <span data-ttu-id="96b69-590">Outros motivos</span><span class="sxs-lookup"><span data-stu-id="96b69-590">Other Reasons</span></span>                  | <span data-ttu-id="96b69-591">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-591">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-592">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="96b69-592">CLOSURE</span></span>                | <span data-ttu-id="96b69-593">Fechamento da empresa</span><span class="sxs-lookup"><span data-stu-id="96b69-593">Business Closure</span></span>               | <span data-ttu-id="96b69-594">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-594">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-595">DEATH</span><span class="sxs-lookup"><span data-stu-id="96b69-595">DEATH</span></span>                  | <span data-ttu-id="96b69-596">Morte</span><span class="sxs-lookup"><span data-stu-id="96b69-596">Death</span></span>                          | <span data-ttu-id="96b69-597">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-597">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-598">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="96b69-598">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="96b69-599">Licença</span><span class="sxs-lookup"><span data-stu-id="96b69-599">Leave of Absence</span></span>               | <span data-ttu-id="96b69-600">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-600">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-601">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="96b69-601">CONTRACTEND</span></span>            | <span data-ttu-id="96b69-602">Fim do contrato</span><span class="sxs-lookup"><span data-stu-id="96b69-602">End of Contract</span></span>                | <span data-ttu-id="96b69-603">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="96b69-603">Terminate worker</span></span>     |
| <span data-ttu-id="96b69-604">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="96b69-604">SALARYCHANGE</span></span>           | <span data-ttu-id="96b69-605">Alteração de salário</span><span class="sxs-lookup"><span data-stu-id="96b69-605">Change of Salary</span></span>               | <span data-ttu-id="96b69-606">Remuneração</span><span class="sxs-lookup"><span data-stu-id="96b69-606">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="96b69-607">Contrato de trabalho</span><span class="sxs-lookup"><span data-stu-id="96b69-607">Terms of employment</span></span>

<span data-ttu-id="96b69-608">Termos de emprego são usados para criar categorias de termos de emprego.</span><span class="sxs-lookup"><span data-stu-id="96b69-608">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="96b69-609">Os termos são mapeados para o Dayforce como valores de indicador de emprego.</span><span class="sxs-lookup"><span data-stu-id="96b69-609">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="96b69-610">Os termos de emprego e as descrições a seguir são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="96b69-610">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="96b69-611">Contrato de trabalho</span><span class="sxs-lookup"><span data-stu-id="96b69-611">Terms of employment</span></span>   | <span data-ttu-id="96b69-612">descrição</span><span class="sxs-lookup"><span data-stu-id="96b69-612">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="96b69-613">Normal</span><span class="sxs-lookup"><span data-stu-id="96b69-613">Regular</span></span>               | <span data-ttu-id="96b69-614">Normal</span><span class="sxs-lookup"><span data-stu-id="96b69-614">Regular</span></span>     |
| <span data-ttu-id="96b69-615">Direto</span><span class="sxs-lookup"><span data-stu-id="96b69-615">Direct</span></span>                | <span data-ttu-id="96b69-616">Direto</span><span class="sxs-lookup"><span data-stu-id="96b69-616">Direct</span></span>      |
| <span data-ttu-id="96b69-617">Estágio</span><span class="sxs-lookup"><span data-stu-id="96b69-617">Internship</span></span>            | <span data-ttu-id="96b69-618">Estágio</span><span class="sxs-lookup"><span data-stu-id="96b69-618">Internship</span></span>  |
| <span data-ttu-id="96b69-619">Permanente</span><span class="sxs-lookup"><span data-stu-id="96b69-619">Permanent</span></span>             | <span data-ttu-id="96b69-620">Permanente</span><span class="sxs-lookup"><span data-stu-id="96b69-620">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="96b69-621">Estado civil</span><span class="sxs-lookup"><span data-stu-id="96b69-621">Marital status</span></span>

<span data-ttu-id="96b69-622">Os valores do estado civil são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="96b69-622">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="96b69-623">A tabela a seguir mostra como os valores do estado civil são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="96b69-623">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="96b69-624">Talent</span><span class="sxs-lookup"><span data-stu-id="96b69-624">Talent</span></span>                 | <span data-ttu-id="96b69-625">Dayforce</span><span class="sxs-lookup"><span data-stu-id="96b69-625">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="96b69-626">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="96b69-626">Married</span></span>                | <span data-ttu-id="96b69-627">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="96b69-627">Married</span></span>                   |
| <span data-ttu-id="96b69-628">Única</span><span class="sxs-lookup"><span data-stu-id="96b69-628">Single</span></span>                 | <span data-ttu-id="96b69-629">Única</span><span class="sxs-lookup"><span data-stu-id="96b69-629">Single</span></span>                    |
| <span data-ttu-id="96b69-630">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="96b69-630">Widowed</span></span>                | <span data-ttu-id="96b69-631">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="96b69-631">Widowed</span></span>                   |
| <span data-ttu-id="96b69-632">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="96b69-632">Divorced</span></span>               | <span data-ttu-id="96b69-633">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="96b69-633">Divorced</span></span>                  |
| <span data-ttu-id="96b69-634">Parceria Registrada</span><span class="sxs-lookup"><span data-stu-id="96b69-634">Registered Partnership</span></span> | <span data-ttu-id="96b69-635">Parceiro doméstico</span><span class="sxs-lookup"><span data-stu-id="96b69-635">Domestic Partnership</span></span>      |
| <span data-ttu-id="96b69-636">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="96b69-636">None</span></span>                   | <span data-ttu-id="96b69-637">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="96b69-637">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="96b69-638">Coabitando</span><span class="sxs-lookup"><span data-stu-id="96b69-638">Cohabiting</span></span>             | <span data-ttu-id="96b69-639">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="96b69-639">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="96b69-640">Sexo</span><span class="sxs-lookup"><span data-stu-id="96b69-640">Gender</span></span>

<span data-ttu-id="96b69-641">As designações de gênero são mapeadas para o Dayforce e convertidas, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="96b69-641">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="96b69-642">A tabela a seguir mostra como as designações de gênero são mapeadas para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="96b69-642">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="96b69-643">Talent</span><span class="sxs-lookup"><span data-stu-id="96b69-643">Talent</span></span>       | <span data-ttu-id="96b69-644">Dayforce</span><span class="sxs-lookup"><span data-stu-id="96b69-644">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="96b69-645">Masculino</span><span class="sxs-lookup"><span data-stu-id="96b69-645">Male</span></span>         | <span data-ttu-id="96b69-646">Masculino</span><span class="sxs-lookup"><span data-stu-id="96b69-646">Male</span></span>                      |
| <span data-ttu-id="96b69-647">Feminino</span><span class="sxs-lookup"><span data-stu-id="96b69-647">Female</span></span>       | <span data-ttu-id="96b69-648">Feminino</span><span class="sxs-lookup"><span data-stu-id="96b69-648">Female</span></span>                    |
| <span data-ttu-id="96b69-649">Não específico</span><span class="sxs-lookup"><span data-stu-id="96b69-649">Non-specific</span></span> | <span data-ttu-id="96b69-650">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="96b69-650">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="96b69-651">Forma de pagamento</span><span class="sxs-lookup"><span data-stu-id="96b69-651">Payment method</span></span>

<span data-ttu-id="96b69-652">Os métodos de pagamento dão ao funcionário e à empresa uma maneira de descrever como os funcionários serão pagos.</span><span class="sxs-lookup"><span data-stu-id="96b69-652">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="96b69-653">Os métodos de pagamento são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="96b69-653">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="96b69-654">A tabela a seguir mostra como os métodos de pagamento são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="96b69-654">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="96b69-655">Talent</span><span class="sxs-lookup"><span data-stu-id="96b69-655">Talent</span></span>             | <span data-ttu-id="96b69-656">Dayforce</span><span class="sxs-lookup"><span data-stu-id="96b69-656">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="96b69-657">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="96b69-657">Cash</span></span>               | <span data-ttu-id="96b69-658">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="96b69-658">Cash</span></span>                      |
| <span data-ttu-id="96b69-659">Pagamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="96b69-659">Electronic Payment</span></span> | <span data-ttu-id="96b69-660">Transferência</span><span class="sxs-lookup"><span data-stu-id="96b69-660">Transfer</span></span>                  |
| <span data-ttu-id="96b69-661">Verificação</span><span class="sxs-lookup"><span data-stu-id="96b69-661">Check</span></span>              | <span data-ttu-id="96b69-662">Cheque</span><span class="sxs-lookup"><span data-stu-id="96b69-662">Cheque</span></span>                    |
| <span data-ttu-id="96b69-663">Boleto bancário</span><span class="sxs-lookup"><span data-stu-id="96b69-663">Bank Draft</span></span>         | <span data-ttu-id="96b69-664">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="96b69-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="96b69-665">Outros</span><span class="sxs-lookup"><span data-stu-id="96b69-665">Other</span></span>              | <span data-ttu-id="96b69-666">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="96b69-666">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="96b69-667">Tipo de conta bancária</span><span class="sxs-lookup"><span data-stu-id="96b69-667">Bank account type</span></span>

<span data-ttu-id="96b69-668">Os tipos de conta bancária são usados para pagamentos eletrônicos aos funcionários.</span><span class="sxs-lookup"><span data-stu-id="96b69-668">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="96b69-669">Os tipos de conta bancária são mapeados para o Dayforce como informações da conta de transferência.</span><span class="sxs-lookup"><span data-stu-id="96b69-669">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="96b69-670">Os tipos de conta bancária são convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="96b69-670">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="96b69-671">Talent</span><span class="sxs-lookup"><span data-stu-id="96b69-671">Talent</span></span>            | <span data-ttu-id="96b69-672">Dayforce</span><span class="sxs-lookup"><span data-stu-id="96b69-672">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="96b69-673">Conta corrente</span><span class="sxs-lookup"><span data-stu-id="96b69-673">Checking Account</span></span>  | <span data-ttu-id="96b69-674">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="96b69-674">CheckingAccount</span></span>           |
| <span data-ttu-id="96b69-675">Conta-salário</span><span class="sxs-lookup"><span data-stu-id="96b69-675">Payroll Account</span></span>   | <span data-ttu-id="96b69-676">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="96b69-676">PayrollAccount</span></span>            |
| <span data-ttu-id="96b69-677">Conta de poupança</span><span class="sxs-lookup"><span data-stu-id="96b69-677">Savings Account</span></span>   | <span data-ttu-id="96b69-678">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="96b69-678">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="96b69-679">Conta BankGirot</span><span class="sxs-lookup"><span data-stu-id="96b69-679">BankGirot account</span></span> | <span data-ttu-id="96b69-680">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="96b69-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="96b69-681">Conta PlusGirot</span><span class="sxs-lookup"><span data-stu-id="96b69-681">PlusGirot account</span></span> | <span data-ttu-id="96b69-682">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="96b69-682">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="96b69-683">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="96b69-683">Earning codes</span></span>

<span data-ttu-id="96b69-684">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="96b69-684">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="96b69-685">Os códigos abordam vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="96b69-685">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="96b69-686">Se uma frequência sem suporte for usada, a frequência **Cada pagamento** é usada por padrão para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="96b69-686">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="96b69-687">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="96b69-687">Supported frequencies</span></span>

- <span data-ttu-id="96b69-688">Todas</span><span class="sxs-lookup"><span data-stu-id="96b69-688">All</span></span>
- <span data-ttu-id="96b69-689">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="96b69-689">EVERYPAY</span></span>
- <span data-ttu-id="96b69-690">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="96b69-690">EACHPAYPERIOD</span></span>
- <span data-ttu-id="96b69-691">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="96b69-691">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="96b69-692">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="96b69-692">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="96b69-693">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-693">1OFMTH</span></span>
- <span data-ttu-id="96b69-694">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-694">LASTOFMTH</span></span>
- <span data-ttu-id="96b69-695">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-695">2OFMTH</span></span>
- <span data-ttu-id="96b69-696">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-696">3OFMTH</span></span>
- <span data-ttu-id="96b69-697">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-697">4OFMTH</span></span>
- <span data-ttu-id="96b69-698">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-698">5OFMTH</span></span>
- <span data-ttu-id="96b69-699">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-699">1N2OFMTH</span></span>
- <span data-ttu-id="96b69-700">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-700">3N4OFMTH</span></span>
- <span data-ttu-id="96b69-701">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-701">1N3OFMTH</span></span>
- <span data-ttu-id="96b69-702">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-702">1N4OFMTH</span></span>
- <span data-ttu-id="96b69-703">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-703">2N3OFMTH</span></span>
- <span data-ttu-id="96b69-704">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-704">2N4OFMTH</span></span>
- <span data-ttu-id="96b69-705">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-705">1N2N3OFMTH</span></span>
- <span data-ttu-id="96b69-706">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-706">1N2N4OFMTH</span></span>
- <span data-ttu-id="96b69-707">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-707">1N3N4OFMTH</span></span>
- <span data-ttu-id="96b69-708">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-708">2N3N4OFMTH</span></span>
- <span data-ttu-id="96b69-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="96b69-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="96b69-710">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="96b69-710">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="96b69-711">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="96b69-711">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="96b69-712">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="96b69-712">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="96b69-713">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="96b69-713">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="96b69-714">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="96b69-714">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="96b69-715">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="96b69-715">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="96b69-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="96b69-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="96b69-717">Endereços</span><span class="sxs-lookup"><span data-stu-id="96b69-717">Addresses</span></span>

<span data-ttu-id="96b69-718">A identificação de códigos específicos de país ou região, estado e município (municipalidade) exige formatos específicos que o Dayforce e os provedores no país/na região possam reconhecer.</span><span class="sxs-lookup"><span data-stu-id="96b69-718">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="96b69-719">Embora o formato das cidades seja flexível, todas as cidades devem estar associadas a um estado.</span><span class="sxs-lookup"><span data-stu-id="96b69-719">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="96b69-720">Talent</span><span class="sxs-lookup"><span data-stu-id="96b69-720">Talent</span></span>              | <span data-ttu-id="96b69-721">Dayforce</span><span class="sxs-lookup"><span data-stu-id="96b69-721">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="96b69-722">País/Região</span><span class="sxs-lookup"><span data-stu-id="96b69-722">Country/Region</span></span>      | <span data-ttu-id="96b69-723">Código do País</span><span class="sxs-lookup"><span data-stu-id="96b69-723">Country Code</span></span>          |
| <span data-ttu-id="96b69-724">CEP</span><span class="sxs-lookup"><span data-stu-id="96b69-724">Zip/Postal Code</span></span>     | <span data-ttu-id="96b69-725">CEP</span><span class="sxs-lookup"><span data-stu-id="96b69-725">Postal Code</span></span>           |
| <span data-ttu-id="96b69-726">Estadual</span><span class="sxs-lookup"><span data-stu-id="96b69-726">State</span></span>               | <span data-ttu-id="96b69-727">Código de estado</span><span class="sxs-lookup"><span data-stu-id="96b69-727">State Code</span></span>            |
| <span data-ttu-id="96b69-728">Cidade</span><span class="sxs-lookup"><span data-stu-id="96b69-728">City</span></span>                | <span data-ttu-id="96b69-729">Cidade</span><span class="sxs-lookup"><span data-stu-id="96b69-729">City</span></span>                  |
| <span data-ttu-id="96b69-730">Região</span><span class="sxs-lookup"><span data-stu-id="96b69-730">County</span></span>              | <span data-ttu-id="96b69-731">Município (municipalidade)</span><span class="sxs-lookup"><span data-stu-id="96b69-731">County (Municipality)</span></span> |
| <span data-ttu-id="96b69-732">Rua</span><span class="sxs-lookup"><span data-stu-id="96b69-732">Street</span></span>              | <span data-ttu-id="96b69-733">Linha de endereço 1</span><span class="sxs-lookup"><span data-stu-id="96b69-733">Address Line 1</span></span>        |
| <span data-ttu-id="96b69-734">Número</span><span class="sxs-lookup"><span data-stu-id="96b69-734">Street Number</span></span>       | <span data-ttu-id="96b69-735">Linha de endereço 2</span><span class="sxs-lookup"><span data-stu-id="96b69-735">Address Line 2</span></span>        |
| <span data-ttu-id="96b69-736">Complemento do edifício</span><span class="sxs-lookup"><span data-stu-id="96b69-736">Building Complement</span></span> | <span data-ttu-id="96b69-737">Linha de endereço 5</span><span class="sxs-lookup"><span data-stu-id="96b69-737">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="96b69-738">Número do passaporte</span><span class="sxs-lookup"><span data-stu-id="96b69-738">Passport number</span></span>

<span data-ttu-id="96b69-739">Os funcionários podem declarar as informações do passaporte.</span><span class="sxs-lookup"><span data-stu-id="96b69-739">Employees can declare passport information.</span></span> <span data-ttu-id="96b69-740">Essas informações são do tipo de identificação **Passaporte** e estão integradas ao Dayforce como parte das informações específicas do México de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="96b69-740">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="96b69-741">Tipo de identificação = "Passaporte"</span><span class="sxs-lookup"><span data-stu-id="96b69-741">Identification Type = "Passport"</span></span>
- <span data-ttu-id="96b69-742">Data da emissão</span><span class="sxs-lookup"><span data-stu-id="96b69-742">Issued Date</span></span>
- <span data-ttu-id="96b69-743">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="96b69-743">Expiration Date</span></span>

<span data-ttu-id="96b69-744">Os funcionários podem declarar vários números de identificação do tipo de identificação **Passaporte**.</span><span class="sxs-lookup"><span data-stu-id="96b69-744">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="96b69-745">No entanto, apenas a entrada atual do passaporte ativo é integrada ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="96b69-745">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="96b69-746">Se todas as entradas do passaporte expirarem, o passaporte emitido mais recentemente será integrado ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="96b69-746">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
