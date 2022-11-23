# Setup

```sh
npm i -D typescript
npm i -D ../../zkoss/zk/build/dts
npx tsc --init
```
Modify `tsconfig.json` to have:
```json
{
    "compilerOptions": {
        "types": ["zk-types"]
    }
}
```
Create a TS file with whatever name (e.g., `demo.ts`) and start typing:
```ts
const oldPanel = zk.augment(zul.wnd.Panel.prototype, {
    onClose(): void {
        alert('Modified zul.wnd.Panel.prototype.onClose');
        return oldPanel.onClose();
    }
})
```