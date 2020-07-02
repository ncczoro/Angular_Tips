## Built-in directive 
###  ngIf
```
    <div *ngIf="isShow; then next else next2"> su dung ngIf then else </div>

    <ng-template #next> then <ng-template>

    <ng-template #next2>  else <ng-template>
```
### ngSwitch
```
    <div [ngSwitch]="myFeature">
        <app-add *ngSwitchCase="'add'"> </app-add>
        <app-delete *ngSwitchCase="'delete'"> </app-delete>
    </div>
```

### ngFor
```
    <div *ngFor="let item of list; let i=index; trackBy: trackItem" > {{i+1}} - {{item}} </div>
    file ts: trackItem(index: number, item: any) {
      //do what ever logic you need to come up with the unique identifier of your item in loop, I will just return the object id.

        return item.id
    }
```
### Template reference variables (#var)
https://stackblitz.com/angular/nlmloddonxm
```
    <input ref-name plaholder="Name"> 
    <button (click)="submit(name.value)">submit</button>

    <form #myForm="ngForm" (ngSubmit)="onSubmit(myForm)"> 
        <input class="form-control" require>
        <button type="submit">Submit</button>
    </form>
```
### @Input, @Ouput properties
https://stackblitz.com/angular/rlqbmeygonqg
### User input
https://stackblitz.com/angular/glqavkqegba
### life cycle hooks
https://stackblitz.com/angular/oyykxqlgyryp
#### ngOnInit(): component fetch its init data (Constructor should do no more than set the initial local variables to simple value). Angular calls ngOnchange() before ngOninit().
#### ngOnDestroy(): to free source
#### ngOnChange(): whenever it detects changes to @input properties of the component or directive
#### ngDoCheck(): to detect a change that Angular overlooked
#### ngAfterViewInit(), ngAfterViewChecked(): calls after it creates a component's child views (@ViewChild). ngAfterViewInint() calls when initialized. ngAfterViewChecked() calls every the views has been checked.
#### ngAfterContentInit(), ngAfterContentChecked(): like afterViewInint(), afterViewChecked()  
- https://stackoverflow.com/questions/34326745/whats-the-difference-between-viewchild-and-contentchild
- viewInit(), viewCheck(): @viewChild
- contentInit(), contentCheck(): @ContentChild