# angular-material-migrate


```
@use '@angular/material' as mat;

$primary: mat.m2-define-palette(mat.$deep-purple-palette);
$accent: mat.m2-define-palette(mat.$amber-palette);
$warn: mat.m2-define-palette(mat.$red-palette);

$theme: mat.m2-define-light-theme((
  color: (
    primary: $primary,
    accent: $accent,
    warn: $warn,
  )
));

@include mat.all-component-themes($theme);

/* M2風の mat-table 調整 */
::ng-deep .mat-mdc-table {
  border-collapse: collapse;
}

::ng-deep .mat-mdc-header-cell {
  background-color: mat.get-color-from-palette($primary, 50); // M2風の薄い色
  font-weight: 500;
  padding: 0 24px;
  height: 56px;
}

::ng-deep .mat-mdc-cell {
  border-bottom: 1px solid rgba(0, 0, 0, 0.12);
  padding: 0 24px;
  height: 48px;
}
```

