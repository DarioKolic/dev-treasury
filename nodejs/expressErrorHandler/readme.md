# Express Error Handler

### Typescript
```
interface IExpressErrorHandler {
    code: string;
    statusCode: number;
}

export default class ExpressErrorHandler extends Error {
  readonly code: string;
  readonly statusCode: number;

  constructor(message: string, apiError: IExpressErrorHandler) {
    super(message);
    this.code = apiError.code;
    this.statusCode = apiError.statusCode;
  }
}
```

### Javascript
```
const DEFAULT_ERROR = {
    code: 'bad.request',
    statusCode: 503
}

export default class ExpressErrorHandler extends Error {
  constructor(message, apiError = DEFAULT_ERROR) {
    super(message);
    this.code = apiError.code;
    this.statusCode = apiError.statusCode;
  }
}
```

## Use as middleware: 

NOTE: Must be last middleware registered

### Typescript
```
app.use((err: ExpressErrorHandler, req: IRequest, res: Response, next: NextFunction) => {
        console.error(err); // Or your own logger

        res
            .status(err.httpStatus)
            .json(getStatusResponse(err.httpStatus, err.message))

        return next();
    })
```

### Javascript
```
app.use((err, req, res, next) => {
        console.error(err) // Or your own logger

        res
            .status(err.httpStatus)
            .json(getStatusResponse(err.httpStatus, err.message))

        return next()
    })
```