# AppPractice

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 12.0.2.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.


`En este proyecto utilizamos`


const rutas :Routes=[ //We need inyect into app.Component.html  => <router-outlet></router-outlet>
    { path:'componente1/:id',component:FooterComponent},
    {  path:'componente2/:id/:titulo',component:Footer2Component},
    {  path:'**',component:BodyComponent}
]

---------------

export class FooterComponent implements OnInit {
//Para recibir el parametro de URL creamos 2 paramar de routeo  ActivateRoute , y Router en el constructor
//Imporrt Router, ActivatedRoute  de @angular/router
  constructor(private activateRoute :ActivatedRoute, private router :Router) { 

  }

  ngOnInit(): void {
    this.activateRoute.params.subscribe( item => {
      if(item["id"] != null){
          console.log('El parametro recibido es ...'+ item["id"]);
      }
    });
  }

}
