# 1 - se guarda la instancia

```java
@Override
	protected void onSaveInstanceState(Bundle outState) {
		outState.putParcelable(BARCODE_KEY, barcodeResult);
		outState.putParcelable("ECRCAMERA",selectedData);
		super.onSaveInstanceState(outState);
}
```

## Librerias

```java
import com.google.android.gms.common.internal.safeparcel.SafeParcelable;
import com.google.android.gms.vision.barcode.zzb;
```

Nota: los objetos para poder ser PARCELABLE debem implementar el siguiente metodo:

```java
implements SafeParcelable
```

Y sus respectivos metodos, asi como la siguiente constante

```java
public static final zzb CREATOR = new zzb();
```

# 2 - Se recupera la instancia en el onCreate

```java
if(savedInstanceState != null){
    ListItemDetail tempSelect = savedInstanceState.getParcelable("ECRCAMERA");

    if (tempSelect != null){
        selectedData = tempSelect;
    }
}

