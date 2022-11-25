# TypeScript Declarations for the ZK Framework

## Using this repo
1. Clone this repo
2. Modify `demo.ts`
3. Compile with `npx tsc`
4. See the output `demo.js` and copy it to your zk project.

## Manually install `zk-types` in your custom repo

1. Install `typescript` and `zk-types` with NPM
```sh
npm i -D typescript zk-types
npx tsc --init // This will create a template tsconfig.json
```
2. Modify `tsconfig.json` to have:
```json
{
    "compilerOptions": {
        "types": ["zk-types"]
    }
}
```
3. Create a TS file with whatever name (e.g., `demo.ts`) and start typing:
```ts
const oldPanel = zk.augment(zul.wnd.Panel.prototype, {
    onClose(): void {
        alert('Modified zul.wnd.Panel.prototype.onClose');
        return oldPanel.onClose();
    }
})
```
4. Read the first section.