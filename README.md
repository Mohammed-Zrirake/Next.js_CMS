# Next.js CMS - Stellar Landing Page

This repository contains a Next.js CMS project based on the "Stellar" landing page template.  It features authentication, various page layouts, component examples, and integrations using Contentful as a headless CMS.

## Features and Functionality

*   **Authentication:** Includes sign-in, sign-up, and reset password pages with a shared authentication layout and logo component.
*   **Landing Page:** A comprehensive landing page with various sections such as hero, logo wall, features, testimonials, and call-to-action.
*   **About Page:** Details the story and team behind the Stellar platform.
*   **Customers Page:** Showcases customer stories and testimonials.  Customer data is fetched dynamically.
*   **Integrations Page:** Highlights integrations with various services across different categories (Engineering, No-code, Collaboration, Productivity).
*   **Changelog Page:** Displays updates and improvements to the Stellar platform.
*   **Pricing Page:** Offers flexible pricing plans with features.
*   **Draft Mode:** Implements Contentful draft mode preview functionality.
*   **Contentful Integration:** Leverages Contentful as a headless CMS to manage dynamic content like customer logos, hero section content, navigation links, and customer posts.

## Technology Stack

*   **Next.js:** A React framework for building server-rendered applications.
*   **React:** A JavaScript library for building user interfaces.
*   **Contentful:** A headless CMS to manage content.
*   **Tailwind CSS:** For styling.
*   **Swiper.js:** For carousels.
*   **AOS (Animate On Scroll):** For animations on scroll.
*   `date-fns`: For date formatting.
*   `@contentful/rich-text-react-renderer`: For rendering rich text from Contentful.

## Prerequisites

Before you begin, ensure you have the following installed:

*   **Node.js:** Version 18 or later.
*   **npm** or **yarn:** Package manager.
*   **Contentful Account:**  You'll need a Contentful account to set up your CMS.
*   **Contentful Space ID and Access Tokens:**  You'll need these to connect your Next.js application to Contentful.

## Installation Instructions

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/Mohammed-Zrirake/Next.js_CMS.git
    cd Next.js_CMS
    ```

2.  **Install dependencies:**

    ```bash
    npm install  # Or yarn install
    ```

3.  **Set up Environment Variables:**

    Create a `.env.local` file in the root directory of your project and add the following environment variables, replacing the placeholder values with your actual Contentful credentials:

    ```
    CONTENTFUL_SPACE_ID=<YOUR_CONTENTFUL_SPACE_ID>
    CONTENTFUL_ACCESS_TOKEN=<YOUR_CONTENTFUL_ACCESS_TOKEN>
    CONTENTFUL_PREVIEW_ACCESS_TOKEN=<YOUR_CONTENTFUL_PREVIEW_ACCESS_TOKEN>
    CONTENTFUL_PREVIEW_SECRET=<YOUR_SECRET_PREVIEW_TOKEN>
    ```
    `CONTENTFUL_PREVIEW_SECRET` can be any string

4.  **Run the development server:**

    ```bash
    npm run dev  # Or yarn dev
    ```

    Open your browser and navigate to `http://localhost:3000` to view the application.

## Usage Guide

### Connecting to Contentful

The application fetches data from Contentful using GraphQL queries.  The queries are located in `content/queries.ts`.

The `contentGQLQuery` function in `content/fetch.ts` handles the communication with the Contentful GraphQL API.  The environment variables defined in `.env.local` are used to authenticate with Contentful.

### Enabling Draft Mode

To enable draft mode for previewing content directly from Contentful:

1.  Navigate to `app/api/draft/route.ts`.
2.  Ensure the `CONTENTFUL_PREVIEW_SECRET` environment variable is set.
3.  Access the following URL in your browser, replacing `<YOUR_SECRET_PREVIEW_TOKEN>` with your secret token:
    ```
    http://localhost:3000/api/draft?secret=<YOUR_SECRET_PREVIEW_TOKEN>
    ```

4.   To disable draft mode:

    ```
    http://localhost:3000/api/disable-draft
    ```

### Adding and Managing Content

1.  Log in to your Contentful account.
2.  Navigate to your space.
3.  Create and manage content types and entries as needed.
4.  Ensure your content types match the GraphQL queries defined in `content/queries.ts`.

### Key File Locations

*   **Components:** Located in the `components/` directory.
*   **Pages:** Located in the `app/` directory.
*   **Contentful Queries:** Located in the `content/queries.ts` file.
*   **CSS Styles:** Global styles are located in `app/css/style.css`.
*   **Environment Variables:** Stored in the `.env.local` file.
*   **Draft Mode API routes:** Located in `app/api/draft/route.ts` and `app/api/disable-draft/route.ts`

## API Documentation

The project interacts with the Contentful GraphQL API. You can explore the API schema and execute queries using the Contentful GraphQL playground:

```
https://graphql.contentful.com/content/v1/spaces/<YOUR_CONTENTFUL_SPACE_ID>/explore?access_token=<YOUR_CONTENTFUL_ACCESS_TOKEN>
```

## Contributing Guidelines

Contributions are welcome! Please follow these guidelines:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Make your changes and commit them with descriptive commit messages.
4.  Submit a pull request to the `main` branch.

## License Information

License not specified.

## Contact/Support Information

For questions or support, please contact Mohammed Zrirake through Github.