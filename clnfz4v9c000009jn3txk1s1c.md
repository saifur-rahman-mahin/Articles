---
title: "Reusable components concept in React"
seoTitle: "Reusable components concept in React"
seoDescription: "Reusable components are a fundamental concept in React, a popular JavaScript library for building user interfaces. React allows you to create UI components"
datePublished: Sat Oct 07 2023 11:50:46 GMT+0000 (Coordinated Universal Time)
cuid: clnfz4v9c000009jn3txk1s1c
slug: reusable-components-concept-in-react
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/4hbJ-eymZ1o/upload/95cd84a508e50e9f9dd09291a2d511cf.jpeg
tags: javascript, reactjs

---

Reusable components are a fundamental concept in React, a popular JavaScript library for building user interfaces. React allows you to create UI components that can be used and reused throughout your application, making it easier to maintain and scale your codebase. Here are some key concepts and practices for creating reusable components in React:

# **1\. Single Responsibility Principle (SRP):**

* **Principle**: A component should have a single responsibility.
    
* **Examples**:
    
    * Component: "UserAuthentication"
        
        * Problem: Handles both login and registration logic.
            
        * Solution: Split into "Login" and "Registration" components.
            
    * Component: "UserProfile"
        
        * Problem: Manages user data display and profile editing.
            
        * Solution: Create "UserProfileDisplay" and "UserProfileEdit" components.
            
    * Component: "NotificationManager"
        
        * Problem: Manages displaying notifications and their lifecycle.
            
        * Solution: Split into "NotificationDisplay" and "NotificationController" components.
            

# **2\. Don't Repeat Yourself (DRY):**

* **Principle**: Avoid duplicating code and maintain a single source of truth.
    
* **Examples**:
    
    * Component: "ProductCard"
        
        * Problem: Duplicated product card design.
            
        * Solution: Extract a reusable "ProductCard" component.
            
    * Component: "Modal"
        
        * Problem: Repeated modal dialog code.
            
        * Solution: Create a generic "Modal" component.
            
    * Component: "ErrorBoundary"
        
        * Problem: Repeated error boundary logic.
            
        * Solution: Create a single "ErrorBoundary" component for reuse.
            

# **3\. Separation of Concerns (SoC):**

* **Principle**: Divide a component into logical parts with distinct responsibilities.
    
* **Examples**:
    
    * Components: "Header" and "Footer"
        
        * Problem: Mix UI and data fetching logic.
            
        * Solution: Create "HeaderContainer" and "FooterContainer" for data fetching.
            
    * Components: "ChatList" and "ChatRoom"
        
        * Problem: Mix chat room management and UI rendering.
            
        * Solution: Use "ChatListContainer" for data and "ChatRoom" for rendering.
            
    * Components: "SearchBar" and "SearchResults"
        
        * Problem: Combine search query and result display.
            
        * Solution: Split into "SearchBar" and "SearchResults" components.
            

# **4\. Component Composition:**

* **Principle**: Build complex components by combining smaller, reusable components.
    
* **Examples**:
    
    * Component: "Dashboard"
        
        * Problem: Complex dashboard with widgets.
            
        * Solution: Compose using "WeatherWidget," "SalesChart," and "TaskList."
            
    * Component: "ProductPage"
        
        * Problem: Detailed product page with various sections.
            
        * Solution: Compose with "ProductDescription," "ProductReviews," and "RelatedProducts."
            
    * Component: "UserProfile"
        
        * Problem: User profile page with multiple sections.
            
        * Solution: Compose using "PersonalInfo," "ActivityHistory," and "Preferences."
            

# **5\. Props and Prop Types:**

* **Principle**: Define and validate component props.
    
* **Examples**:
    
    * Component: "UserCard"
        
        * Problem: Undefined prop types.
            
        * Solution: Define prop types for "UserCard."
            
    * Component: "ProductList"
        
        * Problem: Unvalidated product data props.
            
        * Solution: Define prop types for "ProductList."
            
    * Component: "Navbar"
        
        * Problem: Unenforced prop types for links.
            
        * Solution: Specify prop types for "Navbar" links.
            

# **6\. State Management:**

* **Principle**: Manage state efficiently and avoid duplicating state logic.
    
* **Examples**:
    
    * Components: "ShoppingCart" and "ProductList"
        
        * Problem: Separate shopping cart state.
            
        * Solution: Lift cart state to a shared component.
            
    * Component: "CommentBox"
        
        * Problem: Uncoordinated comment state.
            
        * Solution: Use local state for comments.
            
    * Components: "FilterPanel" and "FilteredResults"
        
        * Problem: Unsynced filter options and results.
            
        * Solution: Lift filter state to a common parent component.
            

# **7\. Container vs. Presentational Components:**

* **Principle**: Separate components into containers (for logic) and presentational (for UI).
    

* **Examples**:
    
    * Components: "UserProfileContainer" and "UserProfile"
        
        * Problem: Mix data fetching and UI rendering.
            
        * Solution: Separate with "UserProfileContainer" and "UserProfile."
            
    * Components: "BlogPostListContainer" and "BlogPostList"
        
        * Problem: Combine data fetching and rendering.
            
        * Solution: Create "BlogPostListContainer" and "BlogPostList."
            
    * Components: "ChatRoomContainer" and "ChatRoom"
        
        * Problem: Combine data fetching and rendering.
            
        * Solution: Divide into "ChatRoomContainer" and "ChatRoom."
            

# **8\. Avoid Mutations:**

* **Principle**: Avoid direct data mutations.
    
* **Examples**:
    
    * Component: "OrderHistory"
        
        * Problem: Modify original order data.
            
        * Solution: Create new order records for changes.
            
    * Component: "InventoryEditor"
        
        * Problem: Allow direct inventory mutations.
            
        * Solution: Implement inventory history for changes.
            
    * Component: "UserProfileEditor"
        
        * Problem: Allow direct user profile updates.
            
        * Solution: Record changes as new user profile versions.
            

# **9\. Use React Hooks:**

* **Principle**: Utilize hooks for state management and lifecycle behavior.
    
* **Examples**:
    
    * Component: "Counter"
        
        * Problem: Class component with state and lifecycle methods.
            
        * Solution: Rewrite as a functional component with `useState`.
            
    * Component: "Timer"
        
        * Problem: Class component with lifecycle methods.
            
        * Solution: Convert to a functional component with `useState` and `useEffect`.
            
    * Component: "DataFetcher"
        
        * Problem: Fetching data in a class component.
            
        * Solution: Refactor as a functional component with `useEffect`.
            

# **10\. Testing and Documentation:**

* **Principle**: Write tests and provide documentation.
    
* **Examples**:
    
    * Component: "Calendar"
        
        * Task: Write unit tests and document usage.
            
        * Problem: Lack of tests and documentation.
            
        * Solution: Create tests and comprehensive documentation.
            
    * Component: "PaymentForm"
        
        * Task: Develop test cases and document.
            
        * Problem: Insufficient tests and documentation.
            
        * Solution: Write test cases and provide clear documentation.
            
    * Component: "UserDashboard"
        
        * Task: Document with usage examples.
            
        * Problem: Inadequate documentation.
            
        * Solution: Enhance documentation with examples.
            

# **11\. Naming Conventions:**

* **Principle**: Maintain consistent and descriptive naming.
    
* **Examples**:
    
    * Components: "ProductThumbnail" and "ProductCard"
        
        * Problem: Inconsistent naming for similar UI elements.
            
        * Solution: Choose either "ProductThumbnail" or "ProductCard" for both.
            
    * Components: "UserAvatar" and "ProfilePicture"
        
        * Problem: Ambiguous and inconsistent names.
            
        * Solution: Use "UserAvatar" for both components.
            
    * Components: "OrderHistoryItem" and "PurchaseRecord"
        
        * Problem: Inconsistent naming for similar UI elements.
            
        * Solution: Use a uniform naming convention, e.g., "OrderHistoryItem," for both components.
            

These principles and examples provide a comprehensive guide to designing React components for maintainability, reusability, and clarity in your code.