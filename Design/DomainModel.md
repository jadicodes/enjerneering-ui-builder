```mermaid
classDiagram
    class WebsiteHub {
    }

    class EditExistingProject {
    }

    class ProjectSetup {
    }

    class StartWithTemplate {
    }

    class StartFromScratch {
    }

    class Workspace {
    }

    class ComponentsSelection {
    }

    class PageBuilder {
    }

    class SaveToJSON {
    }

    WebsiteHub --> EditExistingProject
    WebsiteHub --> ProjectSetup
    ProjectSetup --> StartWithTemplate
    ProjectSetup --> StartFromScratch
    StartFromScratch --> Workspace
    Workspace --> ComponentsSelection
    Workspace --> PageBuilder
    Workspace --> SaveToJSON
    SaveToJSON --> WebsiteHub
    EditExistingProject --> Workspace
