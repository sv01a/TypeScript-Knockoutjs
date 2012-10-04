TypeScript-Knockoutjs
=====================

Example:
<pre>
module app {
    export module models {
        export class contact {
            Id: number = 0;
            Name = ko.observable('');
            SurName = ko.observable('');
            FullName;
            constructor () {
                this.FullName = ko.computed(function () {
                    return this.Name() + " " + this.SurName();
                }, this);
            }
        }
    }
    export module viewModels{
        export class contacts {
            items= ko.observableArray([]);
            addContact(){
                this.items.push(new app.models.contact);
            };
        }
    }
}
var viewModel = new app.viewModels.contacts;
ko.applyBindings(viewModel);
</pre>