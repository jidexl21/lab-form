# Virology & Gene Sequencing Laboratory Service Request Form

Requirements document · Version 1.0 · Based on the client consultation transcript

## 1. Project overview

The proposed application is a web-based laboratory service request form that enables clients to submit samples for virology and gene sequencing services.

The form should provide a simple, Excel-like interface for entering sample details, selecting sequencing requirements, and requesting either standard or expedited processing.

The initial implementation will focus on PCR product sequencing, with the option to expand the supported sample types and laboratory services in the future.

The application should be suitable for hosting on the laboratory's website and potentially integrating with the university's existing digital platform.

## 2. Project objectives

- Provide clients with a convenient way to request laboratory sequencing services.
- Capture the information required by the laboratory to assess and process each request.
- Allow clients to submit multiple samples in a single request.
- Enable clients to select their preferred processing speed and view the applicable service pricing.
- Reduce manual communication and errors when collecting sample information.
- Establish a sustainable digital service that can be hosted and maintained by the laboratory or university.

## 3. Functional requirements

### 3.1 Client information

The form should begin with a section for identifying the client and the organization submitting the request.

| Field                      | Requirement |
| -------------------------- | ----------- |
| Client name                | Required    |
| Email address              | Required    |
| Phone number               | Required    |
| Institution / organization | Required    |
| Department / laboratory    | Optional    |
| Project title or reference | Optional    |
| Additional instructions    | Optional    |

The client's email address should be used for request confirmation and subsequent communication.

### 3.2 Sample information

The sample section is the primary component of the application.

The interface should resemble a spreadsheet, with each sample represented as a row containing the relevant fields. Clients should be able to add or remove rows as required.

Each sample should have a unique identifier within the request.

Sample details — illustrative form

Multiple samples

| Sample ID | Origin | Organism | Amplicon size |
| --------- | ------ | -------- | ------------- |
| S001      | Human  | Virus    | 501–1,000 bp  |
| S002      | Animal | Bacteria | Under 500 bp  |

Illustrative layout only. Actual options and sample-specific fields are defined below.

#### Required sample fields

| Field              | Input type | Options                                    |
| ------------------ | ---------- | ------------------------------------------ |
| Sample ID          | Text       | Client-defined identifier                  |
| Specimen origin    | Dropdown   | Human, Animal, Plant                       |
| Organism category  | Dropdown   | Bacteria, Fungi, Virus                     |
| Product type       | Dropdown   | PCR product                                |
| Amplicon size      | Dropdown   | Under 500 bp; 501–1,000 bp; 1,001–3,000 bp |
| Sample description | Text       | Optional additional details                |

The specimen origin and organism category should be independent fields. For example, a sample may have a human origin and contain a virus.

The form should allow the client to add multiple sample rows without having to restart the request.

### 3.3 Service selection

The client should select the processing speed for the entire request.

Standard sequencing

Estimated turnaround: 14 days

Standard

Fast sequencing

Estimated turnaround: 7 days

Expedited

The service selection must display the corresponding price before the client submits the request.

The laboratory will provide the actual pricing structure, including whether charges are calculated per sample, per sequencing reaction, or per request.

### 3.4 Sample submission and confirmation

The form should include a final review screen summarizing:

- Client and institution information.
- Number of samples submitted.
- Details of each sample.
- Selected processing speed.
- Estimated turnaround time.
- Applicable pricing and any additional charges.

The client should be required to confirm that the information is accurate before submission.

Upon successful submission, the application should generate a unique request reference and display a confirmation message.

The laboratory should receive a notification containing the submitted request details.

## 4. User interface requirements

The application should be designed as a simple, responsive web form with a clean and professional laboratory-oriented appearance.

The key interface requirements are:

1. A clear, step-by-step submission process.
2. A spreadsheet-style sample entry table.
3. Dropdown fields for standardized laboratory information.
4. An Add Sample button for creating additional rows.
5. The ability to edit or remove sample rows before submission.
6. A visible request summary and pricing section.
7. Clear validation messages for missing or invalid information.
8. Responsive layouts for desktop, tablet, and mobile devices.

The form should not require the client to create an account for the initial release.

## 5. Proposed submission workflow

1\. Client information

Enter contact and institution details

2\. Sample details

Add samples and select their characteristics

3\. Service selection

Choose standard or fast processing

4\. Review and submit

Confirm details, pricing, and request submission

5\. Laboratory processing

Receive the request and coordinate sample delivery

## 6. Administrative requirements

The laboratory should have access to an administrative interface for managing incoming requests.

The initial administrative interface should support:

- Viewing submitted requests and their associated samples.
- Searching by request reference, client name, or institution.
- Viewing sample counts and requested processing speeds.
- Exporting request details to Excel or CSV.
- Updating request status.
- Sending a confirmation or follow-up message to the client.

Suggested request statuses:

| Status           | Description                                 |
| ---------------- | ------------------------------------------- |
| Submitted        | Request successfully received               |
| Awaiting samples | Physical samples have not yet been received |
| Received         | Samples received by the laboratory          |
| In progress      | Laboratory processing has commenced         |
| Completed        | Sequencing work completed                   |
| Cancelled        | Request cancelled                           |

## 7. Data and integration requirements

The application should store client details, request information, and individual sample records in a structured database.

Each request should have a unique reference, and each sample should be linked to its parent request.

The data model should support multiple samples per request and allow new sample origins, organism categories, product types, and sequencing services to be added without redesigning the application.

The initial implementation should support:

- A standalone website deployment.
- Export of request information in a structured format.
- Future integration with the university's platform, subject to the university's technical and administrative requirements.

## 8. Security and operational requirements

- The application should use HTTPS for all client submissions.
- Administrative access should be protected by authentication and role-based permissions.
- Sample information and client contact details should only be accessible to authorized personnel.
- The system should retain an audit trail of request submissions and administrative changes.
- The application should be hosted on infrastructure that can be maintained by the laboratory or university.
- Appropriate data retention and privacy policies should be established before the service goes live.

Because the service may involve human-origin biological samples, the laboratory should determine what information is necessary to collect. The initial form should avoid collecting patient names, medical records, or other unnecessary personal health information.

## 9. Scope of the initial release

The minimum viable product should include the following:

| Feature                                      | Initial release                         |
| -------------------------------------------- | --------------------------------------- |
| Client request form                          | Included                                |
| Multiple sample entry                        | Included                                |
| Human, animal, and plant origins             | Included                                |
| Bacteria, fungi, and virus categories        | Included                                |
| PCR product sequencing                       | Included                                |
| Three amplicon size ranges                   | Included                                |
| Standard and fast processing                 | Included                                |
| Pricing display                              | Included, subject to laboratory pricing |
| Request confirmation                         | Included                                |
| Administrative request management            | Included                                |
| University platform integration              | Future phase                            |
| Additional product types                     | Future phase                            |
| DNA submission and other sequencing services | Future phase                            |

## 10. Items requiring confirmation

The transcript establishes the basic form structure and service options. The following details should be confirmed with the laboratory before development is finalized.

Pre-development checklist

7 of 7

Confirm the exact pricing for standard and fast sequencing, including whether pricing is per sample or per request.

Confirm the final amplicon size ranges and whether the boundaries should be under 500 bp, 501–1,000 bp, and 1,001–3,000 bp.

Confirm whether each sample requires a separate sequencing reaction or whether multiple samples can be processed together.

Confirm the maximum number of samples allowed per request, if any.

Confirm whether clients need to upload supporting documents or sample information files.

Confirm the required sample delivery instructions, packaging requirements, and laboratory contact details.

Confirm the university's integration requirements and the preferred hosting arrangement.

## 11. Acceptance criteria

The initial release will be considered ready for deployment when:

- A client can complete and submit a request containing multiple samples.
- The form validates all required information before submission.
- The client can select standard or fast processing and see the applicable price.
- Each request receives a unique reference.
- The laboratory can view and export submitted requests.
- The form works on desktop and mobile devices.
- The application can be deployed independently and is structured for future university integration.

The next step is to confirm the outstanding laboratory details, especially the pricing and sample size ranges, so the first interactive prototype can reflect the actual service offering.
