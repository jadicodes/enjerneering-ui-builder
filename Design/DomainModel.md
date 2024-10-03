classDiagram
    class WebsiteHub {
    }

    class Workshop {
    }

    class EditExistingProject {
    }

    class CreateNewProject {
    }

    class StartWithTemplate {
    }

    class StartFromScratch {
    }

    class ComponentSelection {
    }

    class PageBuilder {
    }

    class SaveToJSON {
    }

    WebsiteHub --> Workshop : "Log in to access"
    Workshop --> EditExistingProject : "Edit existing project"
    Workshop --> CreateNewProject : "Create new project"
    CreateNewProject --> StartWithTemplate : "Start with template"
    CreateNewProject --> StartFromScratch : "Start from scratch"
    StartFromScratch --> ComponentSelection : "Select components"
    StartFromScratch --> PageBuilder : "Build pages"
    PageBuilder --> SaveToJSON : "Save project as JSON"
    SaveToJSON --> CreateNewProject : "Project data saved"
    EditExistingProject --> ComponentSelection : "Modify components"
    EditExistingProject --> PageBuilder : "Modify pages"

    SaveToJSON --> WebsiteHub : "Framework code generated"
